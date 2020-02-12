<template>
  <div class="bg-grey-lighter min-h-screen">
    <!-- intro -->
    <section class="container mx-auto py-4 px-4">
      <h2 id="about-me" class="my-4">About Me</h2>
      <div class="flex flex-wrap items-start">
        <div class="w-full rounded bg-white outline border border-grey-light flex flex-col justify-between leading-normal flex-auto h-full p-4">
          <div class="flex flex-row">
            <div>
              <div class="flex flex-row align-end">
                <h1 class="self-start leading-none">Ankit Singhaniya</h1>
                <span class="self-start rounded-full bg-green uppercase px-2 py-1 text-xs text-white font-bold mr-3 ml-4 mt-1 md:block hidden">
                  Available
                </span>
              </div>

              <h3 class="text-grey-darkest font-semibold text-sm mb-4 mt-2">Full Stack Software Engineer</h3>
              <div class="social">
                <a
                  target="_blank"
                  href="//github.com/ankitsinghaniyaz"
                  class="no-underline text-black text-2xl pr-3"
                >
                  <i class="icon-github"></i>
                </a>
                <a
                  target="_blank"
                  href="//twitter.com/aks0510"
                  class="no-underline text-black text-2xl pr-3"
                >
                  <i class="icon-twitter"></i>
                </a>
                <a
                  target="_blank"
                  href="//linkedin.com/in/ankitsinghaniyaz"
                  class="no-underline text-black text-2xl pr-3"
                >
                  <i class="icon-linkedin"></i>
                </a>
                <a
                  target="_blank"
                  href="http://classandobjects.com"
                  class="no-underline text-black text-2xl pr-3"
                >
                  <i class="icon-globe"></i>
                </a>
              </div>
            </div>

            <div class="ml-auto sm:block hidden">
              <a href="https://stackexchange.com/users/3517359"><img src="https://stackexchange.com/users/flair/3517359.png?theme=clean" width="208" height="58" alt="profile for aks on Stack Exchange, a network of free, community-driven Q&amp;A sites" title="profile for aks on Stack Exchange, a network of free, community-driven Q&amp;A sites"></a>
            </div>
          </div>
          <p class="mt-4 text-grey-darkest">
            Most of the times you will find me dabbling with some idea unless I am working hard to earn a livelihood. To me, coding is an art, editor my canvas and keywords are my brush. When inspiration strikes, I sit down to paint algorithms, which shall be maintained, extended and tested for the ages to come.
          </p>
          <p class="mt-4 text-grey-darkest">
            Passionate about quality software that runs on the production
            environment. Proven ability to work in a team and contribute as an
            individual. Ability to understand business requirements. Experienced
            doing Agile development with Ruby, JavaScript, Python and Golang .
          </p>
        </div>
      </div>
    </section>

    <!-- projects -->
    <section class="container mx-auto py-4 px-4">
      <h2 id="projects" class="my-4">Projects</h2>
      <project-card
        class="pb-8"
        v-for="project of projects.slice(0, 7)"
        :project="project"
        :key="project.title"
      />

      <div class="flex flex-wrap -mx-2"></div>
      <div class="flex flex-wrap -mx-2">
        <div class="w-full lg:w-1/2 px-2">
          <project-card class="pb-8" :project="projects[7]" no-picture/>
        </div>
        <div class="w-full lg:w-1/2 px-2">
          <project-card class="pb-8" :project="projects[8]" no-picture/>
        </div>
        <div class="w-full lg:w-1/2 px-2">
          <project-card class="pb-8" :project="projects[9]" no-picture/>
        </div>
        <div class="w-full lg:w-1/2 px-2">
          <project-card class="pb-8" :project="projects[10]" no-picture/>
        </div>
      </div>
    </section>

    <!-- testimonials -->
    <section class="container mx-auto py-4 px-4">
      <h2 id="testimonials" class="my-4">Testimonials</h2>
      <div class="flex flex-wrap -mx-2">
        <div class="w-full lg:w-1/3 px-2" v-for="testimony of testimonials" :key="testimony.author">
          <testimony-card class="pb-8" :testimony="testimony"/>
        </div>
      </div>
    </section>

    <!-- blogs -->
    <section class="container mx-auto py-4 px-4">
      <h2 id="blogs" class="my-4">Blogs</h2>
      <div class="flex flex-wrap -mx-2">
        <div class="w-full lg:w-1/3 px-2" v-for="blog of blogs" :key="blog.title">
          <blog-card class="pb-8" :blog="blog"/>
        </div>
      </div>
    </section>

    <!-- contact -->
    <section class="container mx-auto py-4 px-4" id="contact">
      <div class="flex flex-wrap mt-2 mb-4">
        <a
          class="flex mx-auto bg-blue hover:bg-blue-dark text-white font-bold py-4 px-12 rounded no-underline"
          href="mailto:ankit@shareito.com"
          target="_blank"
        >Contact Me</a>
      </div>
    </section>
  </div>
</template>

<script>
import rumie from "@/assets/img/rumie2.png";
import guestnetwork from "@/assets/img/guestnetwork.png";
import skymd from "@/assets/img/skymd.png";
import advertkit from "@/assets/img/advertkit2.png";
import formester from "@/assets/img/fms1.png";
import shareito from "@/assets/img/sto2.png";
import eqc from "@/assets/img/eqc2.png";
import oe from "@/assets/img/oe1.png";
import selectom from "@/assets/img/selectom1.png";
import bfs from "@/assets/img/bfs1.png";
import hr from "@/assets/img/hr1.png";

import vue from "@/assets/img/vuejs_logo.png";
import rails from "@/assets/img/rails_logo.png";
import postgres from "@/assets/img/postgres_logo.png";
import facebook_ads from "@/assets/img/facebook_ads_logo.png";
import elasticsearch from "@/assets/img/elasticsearch_logo.png";
import heroku from "@/assets/img/heroku_logo.svg";
import js from "@/assets/img/js_logo.png";
import bootstrap from "@/assets/img/bootstrap_logo.png";
import vuetify from "@/assets/img/vuetify_logo.png";
import react from "@/assets/img/react_logo.svg";
import webpack from "@/assets/img/webpack_logo.svg";
import redux from "@/assets/img/redux_logo.png";
import python from "@/assets/img/python_logo.png";
import redis from "@/assets/img/redis_logo.svg";
import cucumber from "@/assets/img/cucumber_logo.svg";
import mysql from "@/assets/img/mysql_logo.png";
import android from "@/assets/img/android_logo.png";
import java from "@/assets/img/java_logo.svg";
import go from "@/assets/img/go_logo.jpg";
import angular from "@/assets/img/angular.png";

import alon from "@/assets/img/alon.jpeg";
import bogdan from "@/assets/img/bogdan.jpeg";
import enzo from "@/assets/img/enzo.jpeg";

import ProjectCard from "@/components/ProjectCard";
import TestimonyCard from "@/components/TestimonyCard";
import BlogCard from "@/components/BlogCard";

export default {
  components: { ProjectCard, TestimonyCard, BlogCard },
  data() {
    return {
      projects: [
        {
          title: "SkyMd",
          role: "Software Consultant",
          description:
            "SkyMd is a telemedicine platform for dermatology related problems. It helps a patient get access to the best doctors without ever leaving their home. The app is building using Rails and MySql and supports thousands of active users every month.",
          icons: [rails, angular, mysql],
          link: "https://www.skymd.com/",
          c2a: "Know More",
          thumbnail: skymd
        },
        {
          title: "Rumie",
          role: "Senior Frontend Engineer",
          description:
            "Rumie is a non-profit that makes access to free digital education possible for underserved communities worldwide. We collaborated on revamping the experience for application content managers. The new app built using Vue provides a fast and intuitive way to deal with complex flows.",
          icons: [vue, js],
          link: "https://www.rumie.org",
          c2a: "Know More",
          thumbnail: rumie
        },
        {
          title: "GuestNetworks",
          role: "Frontend Engineer",
          description:
            "GuestNetworks help people monetize public Wi-Fi. We created the dashboard for providers who can then track total conversion, manage leads and track engagement. Also developed related applications which help preview and device setup process.",
          icons: [vue, js],
          link: "https://www.guestnetworks.com/",
          c2a: "Know More",
          thumbnail: guestnetwork
        },
        {
          title: "Formester",
          role: "Full Stack Developer",
          description:
            "A form backend as a service. It makes creating form endpoints for websites very easy. It requires zero programming knowledge. The user has the full control over the look and feel of the form. In Formester validation, spam protection and integration with different CRMs are few clicks away.",
          icons: [rails, vue, js, postgres, bootstrap],
          link: "https://alternativeto.net/software/formester/",
          c2a: "Know More",
          thumbnail: formester
        },
        {
          title: "Shareito",
          role: "Full Stack Developer",
          description:
            "Organizations today rely on multiple software running in the cloud. Sharing access to contributors and stakeholders can be very challenging. Shareito provides a central place to manage this. It helps keep track of suspicious activities, ensures strong password usage and optional 2-factor authentication.",
          icons: [rails, vue, js, postgres, vuetify],
          link: "https://beta.shareito.com/",
          c2a: "Know More",
          thumbnail: shareito
        },
        {
          title: "EquipmentConnect",
          role: "Frontend Developer",
          description:
            "Equipment Connect is Fin-tech startup based out of London, UK. It brings the funder, the equipment supplier and the SME under the same roof for hassle-free and easy equipment finance.",
          icons: [vue, js, webpack],
          link: "https://www.equipmentconnect.co.uk/",
          c2a: "Know More",
          thumbnail: eqc
        },
        {
          title: "OrganizedEffort",
          role: "Frontend Developer",
          description:
            "Organized Effort makes collaboration on open projects easy. It allows organizers to easily create, share and track work. Step by step onboarding for contributors and a lot more. Provides a progressive web application for mobile devices.",
          icons: [vue, js, vuetify, webpack],
          link: "https://www.organizedeffort.com",
          c2a: "Know More",
          thumbnail: oe
        },
        {
          title: "Selectom",
          role: "Backend Developer",
          description:
            "Selectom is a smart marketing platform that connects growing businesses with top marketers. It helps the business choose the right marketing agency or freelancer based on their past performance. Making data-driven decision a reality.",
          icons: [python, redis, mysql, cucumber],
          link: "http://www.selectom.com/",
          c2a: "Know More",
          thumbnail: selectom
        },
        {
          title: "HackerRank",
          role: "Content Creator",
          description:
            "HackerRank is one of the best competitive coding platform. It allows companies screen candidates with the help of tests that check their ability in given technology.",
          icons: [react, redux],
          link: "https://www.hackerrank.com/",
          c2a: "See Questions",
          thumbnail: hr
        },
        {
          title: "Quoted",
          role: "Android Developer",
          description:
            "Quoted allows users to explore new quotes and inspirations from great minds around the globe. It has around 15k+ downloads today on the play store.",
          icons: [android, java, python],
          link:
            "https://play.google.com/store/apps/details?id=com.classandobjects.quoted",
          c2a: "Try App",
          thumbnail: hr
        },
        {
          title: "Ride Companion",
          role: "Full Stack Developer",
          inProgress: true,
          description:
            "RideCompanion android app helps riders stay connected. It provides push voice message, live loction tracking and smart alerting",
          icons: [go, android],
          link: "https://bitbucket.org/ankitsinghaniyaz/ride-companion-api",
          c2a: "See Code",
          thumbnail: hr
        },
        {
          title: "Advertkit",
          role: "Full Stack Developer",
          description:
            "An alternative to Facebook Ads Manager. Manage, monitor and optimize your ads on Facebook Ads platform from a single place. User can create split ads with the intuitive and powerful interface. Track the progress of an ad using goals. Use advanced rules engine to automate boring and manual tasks.",
          icons: [rails, react, redux, postgres, facebook_ads, elasticsearch],
          link: "https://www.advertkit.com",
          c2a: "Find More",
          thumbnail: advertkit
        },
        {
          title: "BeautifulSearch",
          role: "Frontend Developer",
          description:
            "BeautifulSearch is the analytics solution for self hosted ElasticSearch instance. It helps businesses monitor and track insights.",
          icons: [react, redux],
          link: "http://beautifulsearch.netlify.com",
          c2a: "Know More",
          thumbnail: bfs
        }
      ],
      testimonials: [
        {
          author: "Alon Diamant",
          role: "CTO, Selectom",
          avatar: alon,
          message:
            "Ankit is a very proficient developer, who is very quick to learn new technologies and concepts. He quickly dove in deep and generated impressive results of high quality, that are still operational to this day."
        },
        {
          author: "Enzo Zadrima",
          role: "Co-Founder & CTO, EquipmentConnect",
          avatar: enzo,
          message:
            "He is a gifted developer with a rare combination of attention to detail and overall sense for the big picture. He is very passionate about what he does and comes up proactively with improvements ideas."
        },
        {
          author: "Bogdan Arsenie",
          role: "Founder, OrganizedEffort",
          avatar: bogdan,
          message:
            "Ankit is my go to person when I need somebody I can trust to execute any front-end project. He's super attentive, communicates effectively and he will accurately manage your expectations for his time and involvement."
        }
      ],
      blogs: [
        {
          title: "Using Vue.js in Rails",
          excerpt:
            "Choosing a JavaScript framework can be challenging. This blog will help you integrate Vue.js in your Rails project. Vue.js is easy to learn and has a good developer experience.",
          link:
            "https://www.classandobjects.com/tutorial/using_vue_js_with_rails/"
        },
        {
          title: "Problem With React Single Page App",
          excerpt:
            "React is awesome, but the choices to create a single page app with react has challenges. Here I share the issues I faced when creating a react SPA.",
          link:
            "https://classandobjects.com/tutorial/problems_with_react_single_page_app/"
        },
        {
          title: "Create Bottom Toolbar in Android",
          excerpt:
            "Creating an Android toolbar can be sometimes challenging. Create a bottom toolbar like google plus with button feedback, touch effects and lot more.",
          link:
            "http://classandobjects.com/tutorial/create_google_plus_like_toolbar_android/"
        }
      ]
    };
  }
};
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif !important;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
