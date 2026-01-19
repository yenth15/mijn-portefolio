<template>
  <div class="page-W2">
    <router-link to="/" class="terug-knop">Terug naar Home</router-link>
    <br /><br /><br />
    <h1>B1-K1-W2</h1>

    <div class="text-block">
      <h2>Ontwerp</h2>
      <p>
        Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> De eisen en wensen zijn vertaald naar een passend, eenduiding en volledig ontwerp.
      </p>
    </div>

    <div class="documents-column">
      <div
        v-for="(doc, index) in documents"
        :key="index"
      >
        <div class="document-container">
          <div class="iframes-block">
            <h3>{{ doc.title }}</h3>
            <iframe
              v-for="(src, i) in doc.iframes"
              :key="i"
              :src="src"
              width="100%"
              height="400px"
              frameborder="0"
            ></iframe>
          </div>

          <div class="side-block">
            <div class="buttons"
            v-show="![2, 3].includes(index)">
              <button
                v-for="(btn, i) in doc.buttons"
                :key="i"
                @click="() => updateSelectedImage(index, i)"
                :class="{ active: selectedImages[index] === i }"
              >
                {{ btn }}
              </button>
            </div>

            <img
              v-show="![2, 3].includes(index)"
              :src="doc.images[selectedImages[index]]"
              alt="afbeelding"
            />
          </div>
        </div>

        <!-- Extra tekst tussen document 2 en 3 -->
        <div
          v-if="index === 1"
          class="extra-text-block"
        >
          <br /><br /><br /><br />
          <H2>Onderbouwing</H2>
      <p>
        Beoordelingseisen:
        <br />
        <strong>Volledig:</strong> De gemaakte keuzes in het ontwerp zijn onderbouwd met steekhoudende argumenten, waarbij rekening is gehouden met haalbaarbeid, privacy en security.
      </p>
        </div>
        <!-- Extra tekst tussen document 4 en 5 -->
        <div
          v-if="index === 3"
          class="extra-text-block"
        >
          <br /><br /><br />
          <H2>Schematechnieken</H2>
          <p>
            Beoordelingseisen:
            <br />
            <strong>Volledig:</strong> Er zijn gebruik gemaakt van relevante of toepasselijke Schematechnieken (bijv. activiteitendiagram, klassendiagram, ERD use case diagram)
          </p>
        </div>
      </div>
    </div>

    <br /><br /><br />
  </div>
</template>

<script>
export default {
  name: "PageTwo",
  data() {
    return {
      documents: [
        // Document 1
        {
          title: "Behoefte Analyse, DocumentAssistent",
          iframes: ["/doc/BA/behoefteanalyse_DocumentAssistent-10.pdf"],
          buttons: [
            "HomePage | Ontwerp",
            "GooglePage| Ontwerp",
            "TemplatePage | Ontwerp",
            "GenereerPage | Ontwerp",
          ],
          images: [
            "/images/Doc/MockUp5.png",
            "/images/Doc/MockUp6.png",
            "/images/Doc/MockUp7.png",
            "/images/Doc/MockUp8.png",
          ],
        },
        // Document 2
        {
          title: "Behoefte Analyse, Elektroscheppers",
          iframes: ["/doc/BA/behoefteanalyse_website_Electroscheppers-8.pdf"],
          buttons: [
            "LoginPage | Ontwerp",
            "WebchatPage | Ontwerp",
            "InzichtPage | Ontwerp",
            "DocumentPage | Ontwerp",
          ],
          images: [
            "/images/Doc/MockUp1.png",
            "/images/Doc/MockUp2.0.png",
            "/images/Doc/MockUp3.png",
            "/images/Doc/MockUp4.png",
          ],
        },
        // Document 3
                {
          title: "Funtioneel Ontwerp, C++ Game",
          iframes: ["/doc/FO/FunctioneelOntwerp_C++-10.pdf"],
          buttons: [
            "Fetch | UI", //////// Pas naam aan
            "Search| UI",/////// Pas naam aan
            "News | UI",/////// Pas naam aan
            "Pager| UI",/////// Pas naam aan
          ],
          images: [
            "/images/Doc/FetchSortK1.png",
            "/images/Doc/SearchNewsK1.png",
            "/images/Doc/NewsK1.png",
            "/images/Doc/PagerK1.png",
          ],
        },
        // Document 4
        {
          title: "Functioneel Ontwerp, DocumentAssistent",
          iframes: ["/doc/FO/FunctioneelOntwerp_offerte-10.pdf"],
          buttons: [
            "Start | Feeder",////// Pas naam aan
            "Loop | Feeder",////// Pas naam aan
            "Verwerkingen | Feeder",////// Pas naam aan
            "News tekst | Feeder",////// Pas naam aan
          ],
          images: [
            "/images/Doc/FeederStartK2.png",
            "/images/Doc/FeederLoopK2.png",
            "/images/Doc/FeederVerwerkingenK3.png",
            "/images/Doc/FeederNewsTekstK3.png",
          ],
        },

        // Document 5
        {
          title: "Technisch Ontwerp, Elektroscheppers",
          iframes: ["/doc/TO/technischontwerp_Elektroscheppers-2.0.pdf"],
          buttons: [
            "Activiteiten Diagram",
            "DataSchema",
            "Mock-up",
            "WireFrame",
            "Componenten Diagram",
          ],
          images: [
            "/images/Doc/UML_Activiteiten_diagram_Elektroscheppers.png",
            "/images/Doc/Dataschema.png",
            "/images/Doc/MockUp2.0.png",
            "/images/Doc/wireframe_elektroscheppers.png",
            "/images/Doc/conponenten_diagram.png",
          ],
        },
        // Document 6
                {
          title: "Technisch Ontwerp, C++ Game",
          iframes: ["/doc/TO/technischontwerp_C++-10.pdf"],
          buttons: [
            "Mock-up",
            "WireFrame",
          ],
          images: [
            "/images/Doc/MockUp9.png",
            "/images/Doc/wireframe_C++.png",
          ],
        },
      ],
      selectedImages: Array(6).fill(0),
    };
  },
  methods: {
    updateSelectedImage(docIndex, imageIndex) {
      this.selectedImages.splice(docIndex, 1, imageIndex);
    },
  },
};
</script>

<style scoped>
.page-W2 {
  color: white;
  padding: 40px 20px;
  max-width: 1400px;
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

h2,
h3 {
  text-align: center;
  color: #ffd6e0;
  margin-top: 20px;
}

p,
ul,
li {
  text-align: center;
}

ul {
  list-style-position: inside;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

li {
  display: list-item;
}

.text-block {
  margin-bottom: 30px;
  line-height: 1.6;
  width: 100%;
  text-align: center;
}

.documents-column {
  display: flex;
  flex-direction: column;
  gap: 50px;
  align-items: center;
  width: 100%;
}

.document-container {
  display: flex;
  gap: 10px;
  align-items: flex-start;
  flex-wrap: nowrap;
  justify-content: center;
  width: 100%;
}

.iframes-block {
  flex: 2;
  min-width: 400px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: center;
}

.side-block {
  flex: 1;
  min-width: 700px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  width: 100%;
  margin-top: 85px;
  margin-left: 0;
}

.side-block img {
  width: 100%;
  border-radius: 8px;
  object-fit: contain;
}

.iframes-block iframe {
  width: 650px;
  height: 550px;
  border: none;
  border-radius: 8px;
}

.buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
  width: 100%;
}

.buttons button {
  padding: 10px 14px;
  font-size: 14px;
  background-color: #444;
  border: none;
  color: white;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.buttons button:hover {
  background-color: #666;
}

.buttons button.active {
  background-color: #ffcad4;
  color: black;
  font-weight: bold;
}

.extra-text-block {
  text-align: center;
  padding: 10px;
  margin: 30px 0;
  margin-bottom: -80px;
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
