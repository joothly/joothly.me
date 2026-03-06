<script setup lang="ts">
import avatarImg from "./assets/avatar.jpg"
import FooterBox from './components/FooterBox.vue'
import HeaderBox from './components/HeaderBox.vue'
import InfoBox from './components/InfoBox.vue'
import TagListItem from './components/TagListItem.vue'
import TimelineItem from './components/TimelineItem.vue'
import IconEmail from './components/icons/IconEmail.vue'
import IconGlobe from './components/icons/IconGlobe.vue'
import IconScale from './components/icons/IconScale.vue'
</script>

<template>
  <main class="grid">
    <HeaderBox class="full-width" title="Hello I'm Jonas." subtitle="I'm a software engineer." :avatarUrl="avatarImg">
      <p>I have {{ new Date().getFullYear() - 2014 }} years of experience in web development.<br>
        I value clean code, simplicity, and user-centric design.<br>
        I thrive in team environments where I can contribute to a collective vision, mentor others, and build
        maintainable systems.
      </p>
      <strong>Think we'd be a good fit?</strong> Hit me up at <a href="mailto:joothly@gmail.com">joothly@gmail.com</a>.
    </HeaderBox>

    <InfoBox heading="Skills">
      <TagListItem heading="Programming languages" :tags="['JavaScript', 'TypeScript', 'Java', 'Rust', 'Go']" />
      <TagListItem heading="Frameworks" :tags="['Vue.js', 'Node.js', 'Angular', 'Spring Boot', 'JUnit']" />
      <TagListItem heading="Databases" :tags="['PostgreSQL', 'MongoDB', 'Redis', 'MySQL']" />
      <TagListItem heading="DevOps" :tags="['Docker', 'Kubernetes', 'CI/CD', 'GitLab CI', 'Jenkins', 'Git']" />
      <TagListItem heading="Soft skills"
        :tags="['Teamwork', 'Problem Solving', 'Critical Thinking', 'Small wins, scaled', 'English', 'German']" />
    </InfoBox>

    <InfoBox heading="Education">
      <TimelineItem date="2019" position="B.Sc. Media Informatics" company="Technische Hochschule Mittelhessen">
        With a focus on web and mobile applications
      </TimelineItem>
      <TimelineItem date="2012" position="IT assistant & vocational baccalaureate"
        company="Berufskolleg Technik Siegen">
      </TimelineItem>
    </InfoBox>

    <InfoBox heading="Work Experience">
      <TimelineItem date="2019" position="IoT Developer" company="CLOOS Schweißtechnik GmbH">
        IoT platform and SDK development • Server, edge & cloud environments • CI/CD maintenance • Welding production
        vizualization and monitoring • Java, TypeScript , Vue.js, Docker, Kubernetes, Yocto Linux
      </TimelineItem>
      <TimelineItem date="2018" position="Web Development Intern" company="CLOOS Schweißtechnik GmbH">
        Bachelor thesis: OEE calculation • Production data visualization • Data aggregation strategy • Java, TypeScript
      </TimelineItem>
      <TimelineItem date="2017" position="Technical Director" company="Freelance">
        Real-time photo platform for FMX 2018 • REST API • User login system • Go, Javascript
      </TimelineItem>
      <TimelineItem date="2015" position="Web App Developer" company="werdewelt GmbH">
        Custom web applications for clients • Java, Spring Boot, Angular, Docker
      </TimelineItem>
      <TimelineItem date="2014" position="Web Developer" company="werdewelt GmbH">
        Website design implementation • CI/CD pipeline maintenance • Typo3 & WordPress extensions • PHP, JavaScript
      </TimelineItem>
    </InfoBox>

    <FooterBox class="full-width">
      <a href="mailto:joothly@gmail.com">
        <IconEmail /> joothly@gmail.com
      </a>
      <a href="https://joothly.me">
        <IconGlobe /> joothly.me
      </a>
      <template #imprintTrigger>
        <IconScale /> Imprint
      </template>
      <template #imprint>
        <small>Angaben gemäß § 5 TMG</small>
        <div>
          Jonas Schneider • Sandweg 14a • 35745 Herborn • Deutschland <br>
          joothly@gmail.com • https://joothly.me
        </div>
      </template>
    </FooterBox>
  </main>
</template>

<style scoped>
.grid {
  column-count: 1;
  column-gap: var(--grid-gap);
  padding: var(--grid-gap);
  margin: 0 auto;
  max-width: 1200px;

  @media (min-width: 1024px) {
    column-count: 2;
  }
}

.grid>* {
  break-inside: avoid;
  margin-bottom: var(--grid-gap);
}

.full-width {
  column-span: all;
  margin-top: var(--grid-gap);
}
</style>
