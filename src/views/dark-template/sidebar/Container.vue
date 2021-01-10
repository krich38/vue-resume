<template>
  <v-card
    color="grey darken-3"
    dark
  >
    <v-card-text>
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Kyle <span class="light-blue--text text--lighten-3">Richards</span>
        </h1>
        <span>
          Just a software engineer, seeking his next role
        </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection },
  data () {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: 'hello@kylerichards.me',
            },
            {
              name: 'Website',
              icon: 'mdi-web',
              text: 'kylerichards.me',
            },
            {
              name: 'D.O.B',
              icon: 'mdi-cake-variant',
              text: '23 Mar 1994',
            },
            {
              name: 'Location',
              icon: 'mdi-map-marker',
              text: 'Newcastle NSW',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-github-circle',
              text: 'github.com/krich38',
              link: 'https://github.com/krich38',
            },
          ],
        },
        hobbies: {
          title: 'PERSONAL ATTRIBUTES',
          items: [
            { text: 'Leadership' },
            { text: 'Reliability' },
            { text: 'Ability to work unsupervised' },
            { text: 'Management' },
            { text: 'Responsibility' },
          ],
        },
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
