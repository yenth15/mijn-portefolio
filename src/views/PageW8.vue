<template>
  <div class="page-W1">
    <router-link to="/" class="terug-knop">Terug naar Home</router-link>
    <br /><br /><br />
    <h1>B1-W2-K3 | Beoordeling reflecteren</h1>

    <div class="text-block">
      <h2>Feedbackproces</h2>
      <p>Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> De kandidaat benoemt zowel Positieve als verbeterpunten van het proces van zowel eigen als teamprestaties.
      </p>
    </div>

    <div class="text-block">
      <h2>Reactie op feedback</h2>
      <p>Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> De kandidaat reageert actief op ontvangen feedback.
      </p>
      <img src="/images/Doc/FeedbackTips.png" alt="FeedbackenTips" />
      <div class="document-container" style="margin-top: 20px;">
        <iframe
          src="/doc/FB/ReflectieMeetingsenZelfstandigWerken.pdf"
          width="100%"
          height="400"
          frameborder="0"
          allowfullscreen
          title="Reflectie Meetings en Teamwork Document"
        ></iframe>
      </div>
      <div class="document-container" style="margin-top: 20px;">
        <iframe
          src="/doc/FB/Reflectieverslag.pdf"
          width="100%"
          height="400"
          frameborder="0"
          allowfullscreen
          title="Reflectie Meetings en Teamwork Document"
        ></iframe>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'PageW2K3',
};
</script>

<style scoped>
.page-W1 {
  color: white;
  padding: 40px;
  max-width: 900px;
  margin: 0 auto;
  font-family: sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  margin-bottom: 20px;
  color: #ffcad4;
  text-align: center;
}

h2 {
  margin-top: 30px;
  color: #ffd6e0;
  text-align: center;
}

a {
  color: #ffd6e0;
  text-decoration: underline;
}

.text-block {
  margin-bottom: 30px;
  line-height: 1.6;
  text-align: center;
  width: 100%;
}

ul {
  padding-left: 0;
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.document-container iframe {
  border: none;
  border-radius: 8px;
  box-shadow: 0 0 10px #bb657a;
  width: 100%;
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
}
</style>
