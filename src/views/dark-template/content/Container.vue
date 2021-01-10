<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="Who am I?"
      >
        <p>
          First Class Honors graduate of a Bachelor of Computer Science from the University of New England,
          and then completed a Masters of Informational Technology Project Management from Charles Start University.
          I am currently undertaking part time study to complete a Graduate Diploma of Psychology.
        </p>
        <p>
          My current role is Principal Solutions Engineer for Bloomfield Mining,
          where I am a hybrid Solutions Architect and Software Engineering Lead.
          I am seeking my next role due to requirements of a more remote based role.
        </p>
      </content-section>

      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md1>
            <v-icon>
              {{ education.icon }}
            </v-icon>
          </v-flex>
          <v-flex md10>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        id="to-timeline"
        title="Skills"
      >
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }} <b>({{ skill.value }} years)</b>
                </div>
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    prouds: [
      {
        icon  : 'mdi-help-rhombus-outline',
        text  : 'Answered 10M+ questions!',
        source: '(Bytegate.ir post views)',
      },
      {
        icon  : 'mdi-library-music',
        text  : 'Made people enjoy and learn a new language for equivalent of 29+ years (older than myself!)',
        source: '(Bobet.ir and its channel downloads)',
      },
      {
        icon  : 'mdi-timer-sand',
        text  : 'Saved +110 days of time of students, writers and etc!',
        source: '(Delix.ir service usages)',
      },
      {
        icon  : 'mdi-account-multiple',
        text  : 'Tried to cover small part of 7 people expenses.',
        source: '(My awesome colleagues)',
      },
    ],
    educations: [
      {
        icon       : 'mdi-medal',
        title      : 'Bachelor of Computer Science',
        location   : 'University of New England',
        description: 'Became a member of University Academic Association of Computer Science',
      },
      {
        icon       : 'mdi-seal',
        title      : 'Masters of IT Project Management',
        location   : 'Charles Sturt University',
        description: 'Became a member of University Academic Association of Computer Science',
      },
      {
        icon       : 'mdi-trophy',
        title      : 'Graduate Diploma of Psychology',
        location   : 'University of New England',
        description: 'Became a member of University Academic Association of Computer Science',
      },
    ],
    skills: [
      {
        title: '.NET',
        icon : 'mdi-language-php',
        value: 10,
      },
      {
        title: 'Java',
        icon : 'mdi-language-php',
        value: 10,
      },
      {
        title: 'Spring / Spring Boot / Hibernate',
        icon : 'mdi-language-php',
        value: 5,
      },
      {
        title: 'MSSQL / MySQL',
        icon : 'mdi-language-php',
        value: 5,
      },
      {
        title: 'Oracle',
        icon : 'mdi-language-php',
        value: 8,
      },
      {
        title: 'Azure',
        icon : 'mdi-language-php',
        value: 3,
      },
      {
        title: 'AWS',
        icon : 'mdi-language-php',
        value: 2,
      },
      {
        title: 'PHP',
        icon : 'mdi-language-php',
        value: 5,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 8,
      },
      {
        title: 'Laravel Framework',
        icon : 'mdi-laravel',
        value: 2,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 3,
      },
      // { divider: true },
      {
        title: 'Ubuntu Server',
        icon : 'mdi-ubuntu',
        value: 7,
      },
      {
        title: 'CentOS Server',
        icon : 'mdi-linux',
        value: 7,
      },
      {
        title: 'Web Application Security',
        icon : 'mdi-shield-lock',
        value: 8,
      },
      {
        title: 'Test Driven Development',
        icon : 'mdi-test-tube',
        value: 10,
      },
      {
        title: 'CI / CD (Atlassian)',
        icon : 'mdi-truck-fast',
        value: 10,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 7,
      },

      {
        title: 'C/C++',
        icon : 'mdi-language-cpp',
        value: 3,
      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
