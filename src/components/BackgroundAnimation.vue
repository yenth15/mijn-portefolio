<template>
  <canvas ref="canvas" class="background-animation"></canvas>
</template>

<script>
export default {
  name: 'BackgroundAnimation',
  data() {
    return {
      canvas: null,
      ctx: null,
      particles: [],
      particleCount: 75,
      particleMaxDistance: 150,
      rightCircles: [],
      codeSymbols: ['{', '}', '[', ']', '(', ')', '<', '>', '/', '*', '+', '-', '=', ';', ':', '|', '&', '%', '#', '@', '!', '?', '~', '^']
    };
  },
  mounted() {
    this.initCanvas();
    this.createParticles();
    this.createRightCircles();
    this.animate();
    window.addEventListener('resize', this.handleResize);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    initCanvas() {
      this.canvas = this.$refs.canvas;
      this.ctx = this.canvas.getContext('2d');
      this.handleResize();
    },
    handleResize() {
      this.canvas.width = window.innerWidth;
      this.canvas.height = window.innerHeight;
    },
    createParticles() {
      this.particles = [];
      for (let i = 0; i < this.particleCount; i++) {
        this.particles.push({
          x: Math.random() * this.canvas.width,
          y: Math.random() * this.canvas.height,
          vx: (Math.random() - 0.5) * 0.35,
          vy: (Math.random() - 0.5) * 0.35,
          radius: 2
        });
      }
    },
    createRightCircles() {
      this.rightCircles = [];
      const spacing = 25;
      const startY = 20;
      
      for (let y = startY; y < this.canvas.height - 20; y += spacing) {
        this.rightCircles.push({
          x: Math.random() * this.canvas.width,
          y: y,
          size: 8,
          speed: 0.5 + Math.random() * 0.8,
          direction: Math.random() < 0.5 ? -1 : 1,
          symbol: this.codeSymbols[Math.floor(Math.random() * this.codeSymbols.length)]
        });
      }
    },
    animate() {
      this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);
      
      // Draw the large circle in the middle
      const centerX = this.canvas.width / 2;
      const centerY = this.canvas.height / 2;
      const circleRadius = (Math.min(this.canvas.width, this.canvas.height) * 0.45) + 15;
      
      this.ctx.beginPath();
      this.ctx.arc(centerX, centerY, circleRadius, 0, Math.PI * 2);
      this.ctx.fillStyle = 'rgba(255, 255, 255, 0.03)';
      this.ctx.fill();

      // Update and draw right-side circles
      this.rightCircles.forEach(circle => {
        // Move circle in its current direction
        circle.x += circle.speed * circle.direction;

        // If circle goes off screen, reset it
        if (circle.x < -20 || circle.x > this.canvas.width + 20) {
          circle.x = Math.random() * this.canvas.width;
          circle.speed = 0.5 + Math.random() * 0.8;
          circle.direction = Math.random() < 0.5 ? -1 : 1;
          circle.symbol = this.codeSymbols[Math.floor(Math.random() * this.codeSymbols.length)];
        }

        // Draw symbol
        this.ctx.font = '12px monospace';
        this.ctx.fillStyle = 'rgba(255, 255, 255, 0.8)';
        this.ctx.textAlign = 'center';
        this.ctx.textBaseline = 'middle';
        this.ctx.fillText(circle.symbol, circle.x, circle.y);
      });
      
      // Update and draw particles
      this.particles.forEach((particle, i) => {
        particle.x += particle.vx;
        particle.y += particle.vy;
        
        // Bounce off walls
        if (particle.x < 0 || particle.x > this.canvas.width) particle.vx *= -1;
        if (particle.y < 0 || particle.y > this.canvas.height) particle.vy *= -1;
        
        // Draw particle
        this.ctx.beginPath();
        this.ctx.arc(particle.x, particle.y, particle.radius, 0, Math.PI * 2);
        this.ctx.fillStyle = 'rgba(255, 255, 255, 0.5)';
        this.ctx.fill();

        // Draw connections between particles
        this.particles.slice(i + 1).forEach(otherParticle => {
          const dx = particle.x - otherParticle.x;
          const dy = particle.y - otherParticle.y;
          const distance = Math.sqrt(dx * dx + dy * dy);
          
          if (distance < this.particleMaxDistance) {
            this.ctx.beginPath();
            this.ctx.moveTo(particle.x, particle.y);
            this.ctx.lineTo(otherParticle.x, otherParticle.y);
            this.ctx.strokeStyle = `rgba(255, 255, 255, ${0.2 * (1 - distance/this.particleMaxDistance)})`;
            this.ctx.lineWidth = 1;
            this.ctx.stroke();
          }
        });
      });
      
      requestAnimationFrame(this.animate);
    }
  }
};
</script>

<style scoped>
.background-animation {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  pointer-events: none;
}
</style> 