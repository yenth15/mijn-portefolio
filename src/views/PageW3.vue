<template>
  <div class="page-W1">
    <router-link to="/" class="terug-knop">Terug naar Home</router-link>

    <h1>B1-K1-W3</h1>

    <!-- W1 -->
    <section class="text-block">
      <h2>Gerealiseerde functionaliteit</h2>
      <p>Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> Er is voldoende inhoud van de functionaliteit gereageerd binnen de gestelde/geplande tijd.
      </p>

      <img src="/images/FeedBack/h4_Screen.png" alt="Mail van ojo" />
    </section>
        <br />

    <!-- W2 -->
    <section class="text-block">
      <h2>Kwaliteit opgeleverde functionaliteiten</h2>
      <p>Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> De opgeleverde functionaliteiten voldoen aan de eisen en wensen.
      </p>
      <ul>
        <li><a href="https://trello.com/b/N3ZkUKzW/documentassistent" target="_blank">Trello Board | DocumentAssistent</a></li>
        <li><a href="https://trello.com/b/6756SHVX/portfolio-project" target="_blank">Trello Board | Portfolio project</a></li>
      </ul>
      <ul class="inline-list">
        <li>
            <video controls style="width: 100%; max-width: 800px; margin-top: 10px;">
              <source src="/images/Doc/Document assistent.mp4" type="video/mp4" />
            </video>
        </li>
        <li>
            <video controls style="width: 100%; max-width: 800px; margin-top: 10px;">
              <source src="/images/Doc/Klantgesprek.mp4" type="video/mp4" />
            </video>
        </li>
      </ul>
    </section>
        <br />


        
    <!-- W5 -->
    <section class="text-block">
      <h2>Kwaliteit opgeleverde functionaliteiten</h2>
        <p>Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> De opgeleverde functionaliteiten voldoen aan de eisen en wensen.
      </p>
      <ul class="inline-list">
        <img class="mudium-img" src="/images/Code/DocumentAssistentCodeMetComments.png" alt="Code commentaar 1"/>
        <img src="/images/Doc/MappenStructuur.png" alt="Code commentaar 2"/>
       </ul> 
    </section>




    <!-- W3 -->
    <section class="text-block">
      <h2>Kwaliteit code</h2>
      <p>Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> De Kwaliteit van de code is goed.
      </p>
      <ul class="inline-list1">
            <h2>Foute code</h2>
        <li><img src="/images/Code/CodeFout1.png" alt="Slechte Code" /></li>
             <h2>Foute code</h2>
        <li><img src="/images/Code/FouteCode2.png" alt="Slechte Code" /></li>
      </ul>
<br />
      <ul class="inline-list2">
              <h2>Goede code</h2>
        <li><img src="/images/Code/CodeGoed1.png" alt="Goede Code" /></li>
              <h2>Goede code</h2>
        <li><img src="/images/Code/GoedeCode2.png" alt="Goede Code" /></li>
      </ul>
        <br />
      <ul>
      </ul>
    </section>
    <br />

    <!-- W4 -->
    <section class="text-block">
      <h2>Versiebeheer</h2>
      <p>Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> Versiebeheer is effectief toegepast.
      </p>


      <ul class="inline-list">
        <li><img class="large-img" src="/images/Doc/Versiebeheer.png" alt="Beheer code" /></li>
        <li><img class="large-img" src="/images/Doc/versiebeheer_github.png" alt="Git commit geschiedenis" /></li>
      </ul>
    </section>
        <br />


  </div>
</template>

<style>
.page-W1 {
  color: white;
  padding: 40px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  color: #ffd6e0;
  margin-bottom: 30px;
  font-size: 28px;
  text-align: center;
}

h2 {
  margin-top: 30px;
  margin-bottom: -10px;
  color: #ffcad4;
  font-size: 20px;
  text-align: center;
}

h3 {
  margin-top: 20px;
  color: #ffa3b1;
  font-size: 18px;
  text-align: center;
}

.text-block {
  margin-bottom: 40px;
  line-height: 1.6;
  width: 100%;
  text-align: center;
}

ul {
  margin-left: 0;
  list-style-type: disc;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0;
}

.inline-list,
.inline-list1,
.inline-list2 {
  display: flex;
  gap: 15px;
  padding-left: 0;
  list-style: none;
  justify-content: center;
  flex-wrap: wrap;
  width: 100%;
}

.inline-list,
.inline-list1 li,
.inline-list2 li {
  margin-left: 0;
}

.inline-list1 li img,
.inline-list2 li img {
  max-width: 1200px !important;
  width: 100%;
  height: auto;
  object-fit: contain;
  border-radius: 6px;
  display: block;
  transition: none !important;
  transform: none !important;
  pointer-events: none;
}

.inline-list1 li img:hover,
.inline-list2 li img:hover {
  transform: none !important;
  transition: none !important;
}

.text-block img,
.inline-list li img,
.inline-list1 li img,
.inline-list2 li img {
  border-radius: 6px;
  max-width: 100%;
  height: auto;
  display: block;
  object-fit: contain;
  max-width: 450px;
  margin: 0 auto;
}

.text-block > img {
  max-width: 480px;
  margin-top: 10px;
}

.mudium-img {
  max-width: 650px !important;
  width: 100%;
  height: auto;
  object-fit: contain;
  margin: 0 auto;
}

.large-img {
  max-width: 1000px !important;
  width: 100%;
  height: auto;
  object-fit: contain;
  margin: 0 auto;
}

a {
  color: #ffd6e0;
  text-decoration: underline;
}

.terug-knop {
  display: inline-block;
  padding: 12px 24px;
  background-color: #76273a;
  color: white;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
  transition: background-color 0.2s ease;
  margin-bottom: 20px;
}

.terug-knop:hover {
  background: transparent;
  border: 2px solid #bb657a;
  color: #bb657a;
}
</style>
