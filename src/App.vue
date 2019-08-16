<template>
  <div id="app">
    <div class="name-area">
      <h1>Tiberiu Cristian Suciu</h1>
      <div class="line"></div>
    </div>
    <div class="project-list">
      <template v-for="(project, index) in projects">
        <ProjectItem :info="project" :key="index" :colors="selectedColors" />
      </template>
    </div>
  </div>
</template>

<script>
import ProjectItem from './components/ProjectItem.vue'

export default {
  name: 'app',
  components: {
    ProjectItem
  },
  created() {
    this.selectedColors = this.colors[Math.floor(Math.random()*this.colors.length)];
    this.projects.sort(function(a, b) {
        var textA = a.title.toUpperCase();
        var textB = b.title.toUpperCase();
        return (textA < textB) ? -1 : (textA > textB) ? 1 : 0;
    });
  },
  data() {
    return {
      selectedColors: '',
      projects: [
        {
          title: 'Vue21',
          description: 'A multiplayer blackjack application made with VueJS',
          link: 'http://34.219.131.135',
          sourceLink: 'https://github.com/tiberiusuciu/Vue21',
          isReady: true
        },
        {
          title: 'Songify',
          description: 'An application to convert online videos into downloadable mp3 files',
          link: '',
          sourceLink: '',
          isReady: false
        },
        {
          title: 'Resume',
          description: 'An application presenting my resume',
          link: '',
          sourceLink: '',
          isReady: false
        },
        {
          title: 'Blog',
          description: 'A tailor made application for my blog',
          link: '',
          sourceLink: '',
          isReady: false
        },
        {
          title: 'MTGVue',
          description: 'A Magic the Gathering application that lets you play with others',
          link: '',
          sourceLink: 'https://github.com/tiberiusuciu/mtgvue',
          isReady: false
        },
        {
          title: 'Business',
          description: 'An application for anyone to get in contact with me so I can build them websites and applications',
          link: '',
          sourceLink: 'https://github.com/tiberiusuciu/Portfolio',
          isReady: false
        },
        {
          title: 'GameJams',
          description: 'An application that groups all my game jam entries',
          link: '',
          sourceLink: '',
          isReady: false
        },
        {
          title: 'QList',
          description: 'Task Management tool',
          link: '',
          sourceLink: 'https://github.com/tiberiusuciu/QList',
          isReady: false
        },
        {
          title: 'Financial',
          description: 'Personal finance management tool',
          link: '',
          sourceLink: 'https://github.com/tiberiusuciu/financial',
          isReady: false
        },
        {
          title: 'Foodies',
          description: 'Recipe Manager tool',
          link: '',
          sourceLink: 'https://github.com/tiberiusuciu/foodies',
          isReady: false
        },
        {
          title: 'Chopify',
          description: 'Online audio track editor',
          link: '',
          sourceLink: '',
          isReady: false
        },
        {
          title: 'ETS',
          description: 'School application to seek help and offer help',
          link: '',
          sourceLink: '',
          isReady: false
        },
        {
          title: 'rpg-io',
          description: 'Terminal-based MMORPG',
          link: '',
          sourceLink: '',
          isReady: false
        },
      ],
      colors: [
        {
          primary: 'rgba(76,161,175,1)',
          secondary: 'rgba(196,224,229,1)'
        },
        {
          primary: 'rgba(0,82,212,1)',
          secondary: 'rgba(111,177,252,1)'
        },
        {
          primary: 'rgba(71,118,230,1)',
          secondary: 'rgba(142,84,233,1)'
        },
        {
          primary: 'rgba(255,81,47,1)',
          secondary: 'rgba(221,36,118,1)'
        },
        {
          primary: 'rgba(255, 175, 189,1)',
          secondary: 'rgba(255, 195, 160,1)'
        },
        {
          primary: 'rgba(66, 39, 90,1)',
          secondary: 'rgba(115, 75, 109,1)'
        },
        {
          primary: 'rgba(6, 190, 181,1)',
          secondary: 'rgba(72, 177, 191,1)'
        }
      ]
    }
  },
}
</script>

<style>
* {
  margin: 0px;
  padding: 0px;
}

body {
  background-color: ghostwhite;
}

#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: black;
  display: flex;
  height: 100vh;
}

.name-area {
  box-sizing: border-box;
  flex: 1.5;
  padding-top: 375px;
  padding-left: 200px;
  border-right: 1px solid black;
}

.project-list {
  flex: 1;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
  /* background-color: #e6e6e6; */
}

.name-area h1 {
  letter-spacing: 3px;
}

.name-area .line {
  background-color: black;
  width: 240px;
  height: 5px;
  margin-top: 10px;
  margin-left: 10px;
}

@media screen and (max-width: 800px) {
    #app {
      display: flex;
      flex-direction: column;
    }
    .project-list, .name-area {
      flex: none;
      padding: 0px;
    }

    .name-area {
      height: 200px;
      padding-top: 75px;
      padding-left: 10px;
      border-right: none;
      border-bottom: 1px solid black;
    }

    .project-list {
      flex: 1;
    }
}

@media screen and (min-width: 800px) and (max-height: 700px) {
  .name-area {
    box-sizing: border-box;
    flex: 1;
    padding-top: 150px;
    padding-left: 10px;
    /* border-right: 1px solid black; */
  }
}
</style>
