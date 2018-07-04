 <template>
  <div class="projects" id="projects">
    <section class="portfolio-section">
      <h2 class="portfolio-section__title">{{ msg }}</h2>
      <ul class="portfolio-list">
        <li class="portfolio-project">
            <div class="portfolio-project__img-outher">
              <img src="project1.png" alt="" class="portfolio-project__img">
            </div>
            <div>
              <h3 class="portfolio-project__title">Portfolio</h3>
              <p class="portfolio-project__desc">layout, HTML, CSS, JavaScript, Vue.js CLI</p>
              <a class="portfolio-project__link" href="https://github.com/sabinasmalec" target="_blank">repozytorium</a>
          </div>
        </li>
        <li class="portfolio-project">
            <div class="portfolio-project__img-outher">
              <img src="project1.png" alt="" class="portfolio-project__img">
            </div>
            <div>
              <h3 class="portfolio-project__title">Fly wiht us</h3>
              <p class="portfolio-project__desc">html to css, HTML, CSS, JavaScript, Vue.js</p>
              <a class="portfolio-project__link" href="https://github.com/sabinasmalec/fly-with-us" target="_blank">repozytorium</a> |
              <a class="portfolio-project__link" href="https://sabinasmalec.github.io/fly-with-us/src/" target="_blank">demo</a>
          </div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Projects',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.projects {
    background: #2980b9;
}

.portfolio-list {
  list-style: none;
  margin: 0;
  padding: 0;
  color: #ecf0f1;
}
.portfolio-project {
  display: flex;
  margin-bottom: 3rem;
  &__img-outher {
    overflow: hidden;
    max-width: 400px;
    max-height: 200px;
    margin: 0 2rem 0 0;
  }
  &__img {
    max-width: 400px;
    transition: all 0.5s ease;
  }
  &__link {
    color: #ecf0f1;
  }
  &:hover {
    .portfolio-project__img {
      transform:scale(1.05)
    }
  }
}
@media all and (max-width: 576px) {
  .portfolio-project {
    flex-direction: column;
    &__img-outher {
      margin: 0;
    }
  }
}
</style>
