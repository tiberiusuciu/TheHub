<template>
  <div class="project">
        <div class="title-area">
            <div class="project-title">
                <h2>{{info.title}}</h2>
            </div>
            <template v-if="info.isReady">
                <a class="app-link" :href="info.link" target="_blank">
                    <div class="goto-link" :style="{background: colors.primary, background: 'linear-gradient(90deg, ' + colors.primary + '0%, ' + colors.secondary + ' 100%)'}">
                        Visit
                    </div>
                </a>
            </template>
            <template v-else>
                <div class="goto-link in-construction">
                    <i class="fad fa-construction"></i>
                </div>
            </template>
        </div>
        <div class="description-area">
            <div>
                {{info.description}}
            </div>
            <div v-if="info.sourceLink !== ''">
                <a class="sourcelink" :href="info.sourceLink" target="_blank" :style="{color: colors.primary}">
                    (see source <i class="fab fa-github"></i>)
                </a>
            </div>
        </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectItem',
  props: ['info', 'colors']
}
</script>

<style scoped>
    .project {
        /* background-color: #f9f; */
        padding: 20px 20px;
        /* height: 60px; */
        /* border: 1px solid black; */
        /* border-bottom: 1px solid black; */
    }

    .title-area {
        display: flex;
    }

    .project-title {
        flex: 1;
        padding: 4px 0px;
    }

    .goto-link {
        width: 100px;
        line-height: 38px;
        /* background: rgb(208,145,209);
        background: linear-gradient(90deg, rgba(208,145,209,1) 0%, rgba(94,92,232,1) 100%); */
        text-align: center;
        font-weight: bold;
        color: white;
        border-radius: 4px;
        cursor: pointer;
        letter-spacing: 1px;
    }

    .description-area {
        margin-top: 10px;
    }

    .in-construction {
        color: black;
        font-size: 1.5em;
        color: orange;
        --fa-secondary-color: orange;
        --fa-primary-color: black;
        --fa-secondary-opacity: 1.0;
    }
    
    .app-link {
        text-decoration: none;
    }
</style>
