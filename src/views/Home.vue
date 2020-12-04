<template>
  <div class="home">
    <v-row justify="space-around">
      <v-col cols="12" sm="5" md="7">
        <div class="side">
          <Sidebar />
        </div>
      </v-col>
      <v-col cols="12" md="4" class="px-0">
        <div class="content">
          <v-container outlined tile>
            <v-container id="profile" class="ma-0">
              <v-row justify="space-around" class="py-3 px-0">
                <v-avatar size="100" width="100px">
                  <img src="../assets/Ge.jpg" alt="Ge" />
                </v-avatar>
              </v-row>
              <v-card class="text-justify pa-4 ma-1" color="#FFEBEE">
                {{ textprofile }}
              </v-card>
            </v-container>

            <v-container id="projects" class="px-0 ml-0">
              <v-list-item
                v-for="project in projects"
                :key="project.title"
                class="pa-0 projects"
              >
                <v-card class="ma-3 " color="#FCE4EC">
                  <v-card-title v-text="project.title"></v-card-title>
                  <div v-text="project.description" class="pa-3"></div>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn icon :href="project.src">
                      <v-icon v-text="project.icon"></v-icon>
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-list-item>
            </v-container>

            <v-container id="contact">
              <v-list-item v-for="(contact, i) in contacts" :key="i">
                <v-btn
                  :href="contact.href"
                  :color="contact.color"
                  :style="{ color: contact.textcolor }"
                >
                  <v-list-item-icon class="mx-0">
                    <v-icon v-text="contact.icon" class="ma-0 pa-0"></v-icon>
                  </v-list-item-icon>
                  <v-list-item-content
                    v-text="contact.text"
                  ></v-list-item-content>
                </v-btn>
              </v-list-item>
            </v-container>
          </v-container>
        </div>
      </v-col>
    </v-row>
    <Foo />
  </div>
</template>

<script>
import Sidebar from "../components/Sidebar.vue";
import Foo from '../components/Foo.vue';

export default {
  name: "Home",
  components: {
    Sidebar,
    Foo
  },
  data: () => ({
    textprofile:
      "Fresh grad of bachelor informatics from Institute Del. Graduate can't stop me from learning something new. I have such an ordinary live, having meals 3 times a day or sometimes getting cold due to climate changing. I am '98 line and hankful that I'm still alive today. Right now, I'm developing my skills and looking for a job. I interested to join Front End Developer team or Quality Assurance team:)",
    projects: [
      {
        title: "Text Summarization",
        description:
          "This application can generate the title from sequence of sentences. I'm using Python and Google Colabs.",
        icon: "mdi-github",
        src: "https://github.com/gevanggelisa/pba",
      },
      {
        title: "Testing Website",
        description:
          "There are 10 functions selected and then test each function using Selenium with Cucumber and Robot Framework.",
        icon: "mdi-github",
        src: "https://github.com/gevanggelisa/testing",
      },
      {
        title: "Word Correction",
        description:
          "This project is changing the word from a database so it can match to KBBI using Python and Google Colabs. ",
        icon: "mdi-github",
        src: "https://github.com/gevanggelisa/word-correction",
      },
      {
        title: "Rework Website Tanamduit",
        description:
          "This project during my internship about 5 months, where I should build responsive website tanamduit using Wordpress. I work onsite for 3 months while the other 2 months remotely.",
        icon: "mdi-web",
        src: "https://id.tanamduit.com/",
      },
    ],
    contacts: [
      {
        href: "mailto:gracevanggelisa@gmail.com",
        color: "#EFEDE6",
        text: "gracevanggelisa@gmail.com",
        icon: "mdi-gmail",
        textcolor: "#F44336",
      },
      {
        href: "https://github.com/gevanggelisa",
        color: "white",
        text: "gevanggelisa",
        icon: "mdi-github",
        textcolor: "black",
      },
      {
        href: "https://instagram.com/gracevanggelisa",
        color: "#D22F71",
        text: "gracevanggelisa",
        icon: "mdi-instagram",
        textcolor: "white",
      },
      {
        href: "https://linkedin.com/in/grace-e-65b42610a",
        color: "#0073B2",
        text: "grace evanggelisa",
        icon: "mdi-linkedin",
        textcolor: "white",
      },
      {
        href: "https://wa.me/6282364104892",
        color: "#0CC243",
        text: "+62 823 6410 4892",
        icon: "mdi-whatsapp",
        textcolor: "white",
      },
    ],
  }),
};
</script>

<style scoped>
.side {
  position: fixed;
}

.home {
  background: url("../assets/space.jpg");
  height: 100%;
  width: 100%;
  display: grid;
  color: brown;
  overflow-x: hidden;
}

.cards {
  background: transparent !important;
  height: 100%;
}

#profile {
  padding-top: 30vh;
  padding-bottom: 35vh;
}

.projects {
  width: 80%;
}

#contact {
  margin-top: 20vh;
  margin-bottom: 30vh;
  padding-left: 0;
}

@media only screen and (max-width: 960px) {
  .side {
    position: static;
  }

  .content {
    margin-top: 10vh;
  }

  #profile {
    padding-top: 15vh !important;
    width: 100vw;
  }

  #projects {
    width: 100vw;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
}
</style>
