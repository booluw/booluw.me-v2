<template>
  <div class="home">
    <HelloWorld />
    <section class="section">
      <h2 class="heading heading--small" style="color: #ffcb05;">Projects</h2>
      <div class="slider">
        <div class="card card--with-img" v-for="project in projects" :key="project.title">
          <img :src="`${publicPath}img/projects/${project.img}`" class="card__img" alt="" />
          <div class="card__pallete"></div>
          <div class="card__head">
            <a :href="project.url" target="_blank" rel="noreferral" class="card__heading">{{project.title}}</a>
            <h3 class="card__heading card__heading--sub">{{project.date}}</h3>
          </div>
          <p class="card__description">{{project.description}}</p>
          <div class="card__footer">
            <h3 class="card__heading card__heading--footer">Stack</h3>
            <div class="container--flex">
              <div class="chip" v-for="stack in project.stack" :key="stack">{{stack}}</div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="section" style="background-color: #2e0854;">
      <h2 class="heading heading--small" style="color: #ffcb05;">Experience</h2>
      <div class="container--des-flex">
        <div class="card card--experience" v-for="exp in experience" :key="exp.post">
          <i class="ion icon ion-md-star card__icon"></i>
          <div class="card__head">
            <h2 class="card__heading">{{exp.post}}</h2>
            <h3 class="card__heading card__heading--sub">{{exp.org}}</h3>
            <div class="card__description">{{exp.description}}</div>
          </div>
        </div>
      </div>
    </section>
    <section class="section" style="background-color: transparent">
      <h2 class="heading heading--small">Recommendations</h2>
      <div class="container--flex">

      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data() {
    return {
      publicPath: process.env.BASE_URL,
      projects: [
        {
          title: 'Diatheke Empire',
          url: '//diatheke-empire.firebaseapp.com',
          date: 'may, 2020',
          img: 'diatheke.png',
          description: `
            Created pages that handles the landing page, about, and investing in the company. I was also responsible for the hosting of the website on Google's Firebase platform.
          `,
          stack: ['HTML', 'CSS', 'JavaScript', 'Firebase']
        },
        {
          title: 'HikePro',
          url: '//hike-pro.firebaseapp.com',
          date: 'august, 2020',
          img: 'diatheke.png',
          description: `
            Created the Progressive Web App as a volunteer for a hiking group in my area. Features a blog and was hosted and powered by Firebase.
          `,
          stack: ['HTML', 'CSS', 'JavaScript', 'VUE JS', 'PWA', 'SPA', 'Firebase', 'Firestore']
        },
        {
          title: 'Get Change Demo',
          url: '//getchange-demo.firebaseapp.com',
          date: 'august, 2020',
          img: 'diatheke.png',
          description: `
            Created a PWA and SPA for an interview for a Junior VUE JS developer at Emergent Labs.
            Built accordingly and pixel perfect to a Figma design and hosted on Firebase.
            Pages includes: Login In form/page and Dashboard.
          `,
          stack: ['HTML', 'CSS', 'JavaScript', 'VUE JS', 'PWA', 'SPA','API' , 'Firebase']
        }
      ],
      experience: [
        {
          post: 'President',
          org: 'nacoss',
          description: `Served as the Executive President of the National Association of Computer Science Students, FUTMinna chapter.`,
        },
        {
          post: 'Utilities Cordinator',
          org: 'HikePro',
          description: `
            Served as a volunteer for my local hiking group. Was in-charge of the utility supplies for over 10 other members of the group.
            Was also in-charge of designing, developing and deploying the group's website.
          `
        },
        {
          post: 'Lead, Web Committee',
          org: 'LUE - Lets Use Enterprenuership',
          description: `
            Served as the lead developer of five members in LUE (Let's Use Enterprenuership), an NGO created to pioneer enterprenuership
            among Nigerian youths.
          `
        },
        {
          post: 'Founding Member',
          org: 'The Patriots',
          description: `
            Served as an active stakeholder for The Patriots, a community of persons with a vision of reshaping the mindset of Nigerians, and Africans on providing a better continent than we met.
          `
        },
        {
          post: 'Community Moderator',
          org: 'IWB - Ideas Worth Billions',
          description: `
            Served as a moderator for a Facebook community of over 1,000+ members. Was in charge of approving community accepted posts and creating posts
            on nation building, technology and startup discovery.
          `
        }
      ]
    }
  },
}
</script>
