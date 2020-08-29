<template>
  <div class="home">
    <HelloWorld />
    <section class="section">
      <h2 class="heading heading--small">Projects</h2>
      <div class="slider gsap" ref="cards">
        <div class="card card--with-img" v-for="project in projects" :key="project.title">
          <img :src="`${publicPath}img/projects/${project.img}`" class="card__img" :alt="`A screenshot of ${project.title}'s website`" />
          <div class="card__head">
            <a :href="project.url" target="_blank" rel="noreferral" class="card__heading">{{project.title}}</a>
            <h3 class="card__heading card__heading--sub">{{project.date}}</h3>
          </div>
          <div class="container--flex card__tags">
              <div class="chip" v-for="stack in project.stack" :key="stack">{{stack}}</div>
            </div>
          <p class="card__description">{{project.description}}</p>
        </div>
      </div>
    </section>
    <section class="section">
      <h2 class="heading heading--small">Experience</h2>
      <div class="container--des-flex">
        <div class="card card--experience fade" v-for="exp in experience" :key="exp.post" ref="fade">
          <i class="ion icon ion-md-star card__icon"></i>
          <div class="card__head">
            <h2 class="card__heading">{{exp.post}}</h2>
            <h3 class="card__heading card__heading--sub">{{exp.org}}</h3>
            <div class="card__description">{{exp.description}}</div>
          </div>
        </div>
      </div>
    </section>
    <section class="section" style="background-color: transparent" v-if="recommendations.length != 0">
      <h2 class="heading heading--small">Recommendations</h2>
      <div class="slider">
        <div class="card card--recommendation" v-for="recommend in recommendations" :key="recommend.author">
          <p class="card__description">
            {{recommend.description}}
          </p>
          <img :src="`${publicPath}img/people/${recommend.img}`" class="card__img" :alt="`Picture of ${recommend.author} - ${recommend.portfolio}, ${recommend.company}`"/>
          <div class="card__head">
            <h2 class="card__heading">{{recommend.author}}</h2>
            <h3 class="card__heading card__heading--sub">{{recommend.portfolio}} - {{recommend.company}}</h3>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import { gsap } from 'gsap'

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
        },{
          title: 'Cryptowise',
          url: '//cryptowise.com.ng',
          date: 'june, 2020',
          img: 'cryptowise.png',
          description: `
            Created pages that handles the user's dashboard, about, FAQ, and training in the company. I was also responsible for the hosting and database of the website on Google's Firebase platform.
          `,
          stack: ['HTML', 'CSS', 'JavaScript', 'Firebase', 'VUE JS', 'Firestore']
        },
        {
          title: 'HikePro',
          url: '//hike-pro.firebaseapp.com',
          date: 'august, 2020',
          img: 'hikepro.png',
          description: `
            Created the Progressive Web App as a volunteer for a hiking group in my area. Features a blog and was hosted and powered by Firebase.
          `,
          stack: ['HTML', 'CSS', 'JavaScript', 'VUE JS', 'PWA', 'SPA', 'Firebase', 'Firestore']
        },
        {
          title: 'Get Change Demo',
          url: '//getchange-demo.firebaseapp.com',
          date: 'august, 2020',
          img: 'getchange.png',
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
      ],
      recommendations: []
    }
  },
  mounted() {
    const fade = this.$refs.fade

    //TODO: Add scrollTrigger animation
    //tl.to(fade, 3, {opacity: 1, scale: 1})
    fade.forEach(el => {
      gsap.timeline({
        scrollTrigger: {
          trigger: el,
          start: "bottom bottom",
          end: "top top",
          markers: false,
          toggleActions: "play complete play reset"
        }
      }).to(el, {opacity: 1, scale: 1})
    })

  },
}
</script>
<style lang="scss" scoped>
/*.gsap {
  transform: translateX(1000px);
} */
.fade {
  opacity: 0;
  transform: scale(0);
}
</style>