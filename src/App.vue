<script setup>
</script>

<template>
  <main>
    <div class="divider" />
    <div class="information-group">
      <img class="avatar" src="./assets/images/avatar1.jpg" alt="avatar" />
      <div class="information">
        <h1>
          Yihao Liu
          <a href="https://orcid.org/0009-0000-6912-3613" target="_blank">
            <img class="orcid" src="./assets/images/orcid.logo.icon.svg" alt="orcid" />
          </a>
        </h1>
        <div class="description">
          <h3>School of Software</h3>
          <h3>Tsinghua University</h3>
          <h3><a href="mailto:liu-yh23@mails.tsinghua.edu.cn">liu-yh23@mails.tsinghua.edu.cn</a></h3>
        </div>
      </div>
      <a class="starry-link" href="./starry">
        <img class="starry" src="./assets/images/star.svg" alt="starry" />
      </a>
    </div>
    <div class="divider" />
    <div class="interest-group">
      <h2>Research Interests</h2>
      <ul>
        <li>Wireless Sensing</li>
        <li>Internet of Things</li>
      </ul>
    </div>
    <div class="divider" />
    <div class="education-group">
      <h2>Educations</h2>
      <ul>
        <li>Master's Degree in Software Engineering from Tsinghua University, 2023 ~ Now.</li>
        <li>Bachelor's Degree in Software Engineering from Tsinghua University (Rank 1), 2018 ~ 2023.</li>
      </ul>
    </div>
    <div class="divider" />
    <div class="publication-group">
      <h2>Publications</h2>
      <ul>
        <li v-for="paper in papers" :key="paper">
          <span class="label">
            [{{ paper.label }}]
          </span>
          <a :href="paper.doi" target="_blank">
            {{ paper.title }}
          </a>
          <br />
          <span v-for="(author, id) in paper.authors" :key="author" :class="author === 'Yihao Liu' ? 'me' : ''">
            {{ author }}{{ id + 1 === paper.authors.length ? '' : ', ' }}
          </span>
          <span class="me" hidden></span>
          <br />
          In {{ paper.publication }}
        </li>
      </ul>
    </div>
    <div class="divider" />
    <div class="honor-group">
      <h2>Honors</h2>
      <ul>
        <li>Chinese National Scholarship for Undergraduates in 2020.</li>
      </ul>
    </div>
  </main>
</template>

<script>
import contents from './contents'

export default {
  data() {
    return {
      papers: contents.papers
    }
  }
}
</script>

<style scoped>

main {
  width: 80%;
  padding: 20px;
  margin: auto;
  background: #ffffff;
}

.information-group {
  display: flex;
  flex-wrap: wrap;
}

.avatar {
  width: 180px;
  margin-left: 5%;
  margin-right: 5%;
}

.information {
  display: flex;
  flex-flow: column;
  justify-content: space-between;
}

h1 {
  margin-top: 20px;
}

.orcid {
  width: 20px;
  vertical-align: top;
}

h3 {
  margin: 0;
  line-height: 32px;
  font-style: italic;
  font-weight: normal;
  word-break: break-all;
}

.starry-link {
  display: block;
  margin: auto 5% 0 auto;
}

.starry {
  width: 32px;
  height: 32px;
}

h2 {
  margin-left: 5px;
}

ul {
  margin: 10px;
  padding-left: 25px;
}

.label {
  color: red;
}

.me {
  font-weight: bold;
}

</style>
