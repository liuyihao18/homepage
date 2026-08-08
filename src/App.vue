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
      <div class="my-world">
        <a class="starry-link" href="./starry">
          <img class="starry" src="./assets/images/star.svg" alt="starry" />
        </a>
        <a class="mildwind-link" href="./mildwind">
          <img class="mildwind" src="./assets/images/wind.svg" alt="starry" />
        </a>
      </div>
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
        <li>Master's Degree in Software Engineering from Tsinghua University, 2023 ~ 2026.</li>
        <li>Bachelor's Degree in Software Engineering from Tsinghua University, 2018 ~ 2023.</li>
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
          <span class="title">
            <a :href="paper.doi" target="_blank">
              {{ paper.title }}
            </a>
          </span>
          <!--
          <span class="file">
            [<a :href="'./papers/' + paper.file">PDF</a>]
          </span>
          -->
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
        <li>Outstanding Graduate of Tsinghua University, 2026.</li>
        <li>Tsinghua University Graduate Comprehensive Scholarship (First Class), 2025.</li>
        <li>Tsinghua University Graduate Comprehensive Scholarship (First Class), 2024.</li>
        <li>Outstanding Graduate of Tsinghua University, 2023.</li>
        <li>Outstanding Graduate of Beijing, 2023.</li>
        <li>Outstanding Scholarship of Fujian Youth Talent Development Program, 2021.</li>
        <li>Chinese National Scholarship for Undergraduates, 2020.</li>
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

@media (min-width: 750px) {
  .information-group {
    display: flex;
    flex-wrap: wrap;

    .avatar {
      width: 180px;
      margin-left: 5%;
      margin-right: 5%;
    }

    .information {
      display: flex;
      flex-flow: column;
      justify-content: space-between;

      h1 {
        margin-top: 20px;

        .orcid {
          width: 20px;
          vertical-align: top;
        }
      }

      h3 {
        margin: 0;
        line-height: 32px;
        font-style: italic;
        font-weight: normal;
        word-break: break-all;
      }
    }

    .my-world {
      margin-left: auto;

      .starry-link, .mildwind-link {
        display: block;

        .starry, .mildwind {
          width: 32px;
          height: 32px;
        }
      }
    }
  }
}

@media (max-width: 750px) {
  .information-group {
    text-align: center;

    .avatar {
      width: 180px;
      margin-left: 5%;
      margin-right: 5%;
    }

    .information {
      display: flex;
      flex-flow: column;
      justify-content: space-between;

      h1 {
        margin-top: 20px;

        .orcid {
          width: 20px;
          vertical-align: top;
        }
      }

      h3 {
        margin: 0;
        line-height: 32px;
        font-style: italic;
        font-weight: normal;
        word-break: break-all;
      }
    }

    .my-world {
      margin-top: 10px;
      display: block;

      .starry-link, .mildwind-link {
        margin: 5px;

        .starry, .mildwind {
          width: 32px;
          height: 32px;
        }
      }
    }
  }
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
  font-weight: bold;
}

.title {
  a, a:visited {
    color: blue;
  }

  a:hover {
    color: #0033CC;
  }

  a:active {
    color: #000080;
  }
}

.file {
  a, a:visited {
    color: #28A745;
  }

  a:hover {
    color: #218838;
  }

  a:active {
    color: #1C7430;
  }
}

.me {
  font-weight: bold;
}

</style>
