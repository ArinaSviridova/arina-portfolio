<template>
  <main class="page">
    <div class="pageGlow pageGlowOne"></div>
    <div class="pageGlow pageGlowTwo"></div>

    <header class="siteHeader reveal">
      <nav class="nav">
        <a href="#" class="logoLink" aria-label="Arina Svirydava homepage">
          <img :src="logoImage" alt="Arina Svirydava logo" class="logoImage" />
        </a>

        <button
          class="menuButton"
          type="button"
          :class="{ active: isMenuOpen }"
          aria-label="Toggle navigation menu"
          @click="isMenuOpen = !isMenuOpen"
        >
          <span></span>
          <span></span>
        </button>

        <div class="navLinks" :class="{ open: isMenuOpen }">
          <a href="#about" @click="closeMenu">About</a>
          <a href="#services" @click="closeMenu">What I Do</a>
          <a href="#projects" @click="closeMenu">Projects</a>
          <a href="#skills" @click="closeMenu">Skills</a>
          <a href="#contact" @click="closeMenu">Contact</a>
        </div>
      </nav>

      <section class="hero">
        <div class="heroMain">
          <p class="eyebrow">Front-end Developer</p>

          <h1>I build useful, elegant websites.</h1>

          <p class="heroText">
            I’m Arina Svirydava, a front-end developer based in Georgia. I create responsive
            websites, landing pages and digital products, combining front-end development, SEO,
            analytics, content structure and deployment.
          </p>

          <div class="actions">
            <a href="#projects" class="button primary">View Projects</a>
            <a href="#contact" class="button secondary">Contact Me</a>
          </div>
        </div>

        <aside class="heroAside">
          <div class="heroLogoWrap">
            <img :src="logoImage" alt="AS logo" class="heroLogo" />
          </div>

          <div>
            <h2>Arina Svirydava</h2>

            <p>
              Front-end Developer | SEO-friendly Websites, Analytics & Creative Digital Projects
            </p>

            <div class="tagList">
              <span>Vue.js</span>
              <span>JavaScript</span>
              <span>SEO</span>
              <span>Analytics</span>
            </div>
          </div>
        </aside>
      </section>
    </header>

    <section id="about" class="section reveal">
      <div class="sectionIntro">
        <p class="eyebrow">About</p>
        <h2>Frontend, SEO, analytics and content.</h2>
      </div>

      <div class="twoColumns">
        <p>
          I combine front-end development with SEO, analytics, content and visual communication. My
          work is focused on building clean, useful and responsive websites for creative
          professionals, artists, brands, events and small businesses.
        </p>

        <p>
          I can take a project from rough idea to published website: define the structure, write and
          adapt copy, build the interface, optimize images, set up analytics, improve search
          visibility and deploy the final result.
        </p>
      </div>
    </section>

    <section id="services" class="section reveal">
      <div class="sectionIntro">
        <p class="eyebrow">What I Do</p>
        <h2>Websites built for real users.</h2>
      </div>

      <div class="serviceGrid">
        <article v-for="service in services" :key="service.title" class="serviceCard">
          <span class="cardNumber">{{ service.number }}</span>
          <h3>{{ service.title }}</h3>
          <p>{{ service.description }}</p>
        </article>
      </div>
    </section>

    <section id="projects" class="section reveal">
      <div class="sectionIntro">
        <p class="eyebrow">Featured Projects</p>
        <h2>Selected work.</h2>
      </div>

      <div class="projectsList">
        <article v-for="project in projects" :key="project.title" class="projectCard">
          <div class="projectInfo">
            <p class="projectType">{{ project.tag }}</p>

            <h3>{{ project.title }}</h3>

            <p class="projectDescription">
              {{ project.description }}
            </p>

            <ul class="projectList">
              <li v-for="point in project.points" :key="point">
                {{ point }}
              </li>
            </ul>

            <div class="actions">
              <a
                :href="project.url"
                target="_blank"
                rel="noopener noreferrer"
                class="button primary"
              >
                Visit Website
              </a>
            </div>
          </div>

          <div class="projectPreview">
            <div class="previewTop">
              <span></span>
              <span></span>
              <span></span>
            </div>

            <div class="previewBody">
              <p>{{ project.mockupLabel }}</p>
              <h4>{{ project.mockupTitle }}</h4>

              <div class="screenshotsGrid" :class="`screenshots-${project.images.length}`">
                <figure
                  v-for="(image, index) in project.images"
                  :key="image"
                  class="screenshotCard"
                >
                  <img
                    :src="image"
                    :alt="`${project.title} screenshot ${index + 1}`"
                    loading="lazy"
                  />
                </figure>
              </div>
            </div>
          </div>
        </article>
      </div>
    </section>

    <section id="skills" class="section reveal">
      <div class="sectionIntro">
        <p class="eyebrow">Skills</p>
        <h2>My practical tech stack.</h2>
      </div>

      <div class="skillsGrid">
        <article v-for="group in skillGroups" :key="group.title" class="skillCard">
          <h3>{{ group.title }}</h3>

          <div class="tagList">
            <span v-for="skill in group.skills" :key="skill">
              {{ skill }}
            </span>
          </div>
        </article>
      </div>
    </section>

    <section class="section reveal">
      <div class="sectionIntro">
        <p class="eyebrow">Experience</p>
        <h2>Development, content and creative production.</h2>
      </div>

      <div class="timeline">
        <article v-for="item in experience" :key="item.title" class="timelineItem">
          <p class="timelineDate">{{ item.date }}</p>
          <h3>{{ item.title }}</h3>
          <p>{{ item.description }}</p>
        </article>
      </div>
    </section>

    <section id="contact" class="section contactSection reveal">
      <p class="eyebrow">Contact</p>

      <h2>Need a website or digital project?</h2>

      <p>
        I’m open to front-end, creative web and digital project roles, especially where development,
        content, SEO and analytics meet.
      </p>

      <div class="actions contactActions">
        <a href="mailto:krimikarina@gmail.com" class="button primary"> Email Me </a>

        <a
          href="https://t.me/ArinaSvir"
          target="_blank"
          rel="noopener noreferrer"
          class="button secondary"
        >
          Telegram
        </a>

        <a href="tel:+995511198766" class="button secondary"> Call Me </a>

        <a
          href="https://www.linkedin.com/in/arina-svirydava-221761172/"
          target="_blank"
          rel="noopener noreferrer"
          class="button secondary"
        >
          LinkedIn
        </a>
      </div>

      <div class="contactInfo">
        <a href="mailto:krimikarina@gmail.com">krimikarina@gmail.com</a>
        <a href="https://t.me/ArinaSvir" target="_blank" rel="noopener noreferrer">@ArinaSvir</a>
        <a href="tel:+995511198766">+995 511 198 766</a>
      </div>
    </section>
  </main>
</template>

<script setup>
import { onMounted, ref } from 'vue'

import logoImage from './assets/logo.png'

import sacra1 from './assets/sacra-1.png'
import sacra2 from './assets/sacra-2.png'
import sacra3 from './assets/sacra-3.png'
import sacra4 from './assets/sacra-4.png'

import tosti1 from './assets/tosti-1.png'
import tosti2 from './assets/tosti-2.png'
import tosti3 from './assets/tosti-3.png'

const isMenuOpen = ref(false)

const closeMenu = () => {
  isMenuOpen.value = false
}

onMounted(() => {
  const items = document.querySelectorAll('.reveal')

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible')
          observer.unobserve(entry.target)
        }
      })
    },
    {
      threshold: 0.12,
    },
  )

  items.forEach((item) => observer.observe(item))
})

const services = [
  {
    number: '01',
    title: 'Front-end Development',
    description:
      'Responsive websites and landing pages built with HTML, CSS, JavaScript and Vue.js.',
  },
  {
    number: '02',
    title: 'SEO-friendly Websites',
    description:
      'Clean structure, metadata, sitemap, canonical links, hreflang, JSON-LD and technical SEO basics.',
  },
  {
    number: '03',
    title: 'Analytics & Tracking',
    description:
      'Google Search Console, Google Tag Manager, Yandex Metrica and conversion event tracking.',
  },
  {
    number: '04',
    title: 'Creative Digital Projects',
    description:
      'Portfolio websites, artist pages, event promo, content structure and visual communication.',
  },
]

const projects = [
  {
    title: 'Sacraglyph / bazookatattoo',
    tag: 'Bilingual portfolio website',
    url: 'https://sacraglyph.com/',
    mockupLabel: 'Sacraglyph',
    mockupTitle: 'Tattoo artist portfolio website',
    images: [sacra1, sacra2, sacra3, sacra4],
    description:
      'Designed, developed and launched a bilingual portfolio and lead generation website for a tattoo artist based in Georgia.',
    points: [
      'Built a responsive portfolio website with HTML, CSS and JavaScript',
      'Created portfolio galleries, pricing section, merch section and contact flows',
      'Implemented SEO setup: metadata, sitemap, canonical links, hreflang and JSON-LD',
      'Optimized images with WebP / AVIF, lazy loading and performance improvements',
      'Set up Google Search Console, Google Tag Manager and Yandex Metrica tracking',
      'Integrated a contact form with Telegram notifications',
      'Deployed and maintained the website through Netlify',
    ],
  },
  {
    title: 'TostiBudapest',
    tag: 'Digital loyalty card web app',
    url: 'https://tostibudapest.com/',
    mockupLabel: 'TostiBudapest',
    mockupTitle: 'Digital loyalty card web app',
    images: [tosti1, tosti2, tosti3],
    description:
      'Created a digital loyalty card platform for a Budapest coffee shop as part of a startup project, replacing paper stamp cards with a digital customer loyalty system.',
    points: [
      'Led product design, front-end development and usability testing',
      'Built the client-facing digital loyalty card app with HTML, CSS and Vue.js',
      'Developed an admin panel for client management, statistics and user administration',
      'Worked with REST API, Docker, SPA and PWA technologies',
      'Tested usability, functionality and key user flows across the product',
      'Helped replace paper loyalty cards with a more eco-friendly and efficient digital solution',
    ],
  },
]

const skillGroups = [
  {
    title: 'Frontend',
    skills: ['Vue.js', 'JavaScript', 'HTML5', 'CSS3', 'Responsive Layout', 'Git'],
  },
  {
    title: 'Product & Web Apps',
    skills: ['SPA', 'PWA', 'REST API', 'Docker', 'Admin Panels', 'Usability Testing'],
  },
  {
    title: 'SEO & Performance',
    skills: ['Technical SEO', 'JSON-LD', 'Sitemap', 'WebP', 'AVIF', 'Lazy Loading'],
  },
  {
    title: 'Analytics',
    skills: [
      'Google Tag Manager',
      'Google Search Console',
      'Yandex Metrica',
      'Conversion Tracking',
    ],
  },
  {
    title: 'Digital',
    skills: [
      'Content Strategy',
      'Copywriting',
      'Landing Pages',
      'Event Promotion',
      'Visual Communication',
    ],
  },
]

const experience = [
  {
    date: 'Current',
    title: 'Front-end Developer & Digital Project Specialist',
    description:
      'Building responsive websites and landing pages with SEO, analytics, content structure and deployment.',
  },
  {
    date: 'Product Case',
    title: 'TostiBudapest',
    description:
      'Led design, front-end development and usability testing for a digital loyalty card web app built with Vue.js, SPA, PWA, REST API and Docker.',
  },
  {
    date: 'Creative Web Case',
    title: 'Sacraglyph / bazookatattoo',
    description:
      'Designed and launched a bilingual portfolio website for a tattoo artist with galleries, pricing, merch, SEO, analytics and contact form integration.',
  },
  {
    date: 'Creative Projects',
    title: 'Event, Content & Visual Communication',
    description:
      'Working with event promotion, artist communication, social media content and creative project presentation.',
  },
]
</script>
