<template>
  <div class="technologies" id="technologies">

<section class="portfolio-section">
  <h2 class="portfolio-section__title">{{ msg }}</h2>
  <ul class="technologies-list">
    <li class="technologies-list__item" aria-label="HTML5">
      <HtmlIcon class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="CSS3">
      <CssIcon class="technologies-list__icon" />
    </li>

    <li class="technologies-list__item" aria-label="JavaScript">
      <JsLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="VueJS">
      <VuejsLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="jQuery">
      <JqueryLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="SASS">
      <SassLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="GIT">
      <GitLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="Gulp">
      <GulpLogo class="technologies-list__icon icon-gulp" />
    </li>
    <li class="technologies-list__item" aria-label="Webpack">
      <WebpackLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="Bootstrap">
      <BootstrapLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="PHP">
      <PhpLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="mySQL">
      <MysqlLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="Photoshop">
      <PsLogo class="technologies-list__icon" />
    </li>
    <li class="technologies-list__item" aria-label="Wordpress">
      <WordpressLogo class="technologies-list__icon" />
    </li>
  </ul>
</section>
</div>
</template>

<script>
import HtmlIcon from '../assets/img/icon-html.svg';
import CssIcon from '../assets/img/icon-css.svg';
import BootstrapLogo from '../assets/img/icon-bootstrap.svg';
import GitLogo from '../assets/img/icon-git.svg';
import GulpLogo from '../assets/img/icon-gulp.svg';
import JqueryLogo from '../assets/img/icon-jquery.svg';
import JsLogo from '../assets/img/icon-js.svg';
import MysqlLogo from '../assets/img/icon-mysql.svg';
import PhpLogo from '../assets/img/icon-php.svg';
import PsLogo from '../assets/img/icon-ps.svg';
import SassLogo from '../assets/img/icon-sass.svg';
import VuejsLogo from '../assets/img/icon-vuejs.svg';
import WebpackLogo from '../assets/img/icon-webpack.svg';
import WordpressLogo from '../assets/img/icon-wordpress.svg';

export default {
  name: 'HelloWorld',
  components: {
    HtmlIcon,
    CssIcon,
    BootstrapLogo,
    GitLogo,
    GulpLogo,
    JqueryLogo,
    JsLogo,
    MysqlLogo,
    PhpLogo,
    PsLogo,
    SassLogo,
    VuejsLogo,
    WebpackLogo,
    WordpressLogo
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
    margin: 40px 0 0;
}

a {
    color: #42b983;
}
.technologies {
  background: #b0d7d9;
}
.technologies-list {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    &__item {
        margin: 1.5rem 1rem;
    }
    &__icon {
        width: 100px;
        height: 100px;
    }
}
</style>
