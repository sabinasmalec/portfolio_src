<template>
<div class="contact" id="contact">
  <section class="portfolio-section">
    <h2 class="portfolio-section__title portfolio-section__title--p-w">
      <span class="portfolio-section__title-inner">{{ msg }}</span>
    </h2>
    <div class="contact__container">
      <ul class="contact-links">
        <li class="contact-links__item">
          <a class="icon-mail contact-links__link" href="mailto:sabina.smalec@gmail.com">sabina.smalec@gmail.com</a>
        </li>
        <li class="contact-links__item">
          <a class="icon-linkedin contact-links__link" href="https://www.linkedin.com/in/sabina-smalec/" target="_blank">linkedin.com/in/sabina-smalec/</a>
        </li>
        <li class="contact-links__item">
          <a class="icon-github-circled contact-links__link" href="https://github.com/sabinasmalec" target="_blank">github.com/sabinasmalec</a>
        </li>
      </ul>
      <form class="contact-form">
        <label class="contact-form__label" for="input-name">
        Imię i nazwisko
      </label>
        <input class="contact-form__input" id="input-name" type="text" name="name"  v-model="newMessage.name">

        <label class="contact-form__label" for="input-email">
    Email
  </label>
        <input class="contact-form__input" id="input-email" type="email" name="email" v-model="newMessage.email">
        <label class="contact-form__label" for="input-msg">
    Treść
  </label>
        <textarea class="contact-form__textarea" name="message" rows="8" cols="80" v-model="newMessage.message"></textarea>
        <button class="contact-form__submit" type="button" name="button" v-on:click="addMessage">Wyślij</button>
      </form>
    </div>
  </section>
</div>
</template>

<script>
import firebase from 'firebase'
const config = {
  apiKey: "AIzaSyDi78dtuyCSi7Xv4kV7CbWLJokvM7ZO8zU",
  authDomain: "portfolio-contact.firebaseapp.com",
  databaseURL: "https://portfolio-contact.firebaseio.com",
  projectId: "portfolio-contact",
  storageBucket: "portfolio-contact.appspot.com",
  messagingSenderId: "298028804447"
};
const fb = firebase.initializeApp(config);
const db = fb.database()
const messagesRef = db.ref('messages')

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function () {
    return {
      newMessage: {
          name: '',
          email: '',
          message: ''
        }
    }
  },
  methods: {
    addMessage: function () {
        messagesRef.push(this.newMessage)
        this.newMessage.name = ''
        this.newMessage.email = ''
        this.newMessage.message = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
    margin: 40px 0 0;
}
.contact {
    background: #1abc9c;
    &__container {
        display: flex;
        justify-content: space-between;
    }
}
.contact-links {
    display: flex;
    flex-direction: column;
    list-style-type: none;
    padding: 0;
    margin: 0;
    &__item {
        margin-bottom: 1rem;
        font-size: 1.2rem;
    }
    &__link {
        text-decoration: none;
        color: #ecf0f1;
        &:hover {
            color: #8e44ad;
        }
        &::before {
            margin-right: 1rem;
        }
    }
}
.contact-form {
    display: flex;
    flex-direction: column;
    max-width: 90%;
    width: 400px;
    background: #ecf0f1;
    padding: 1rem;
    border-radius: 4px;
    &__label {
        display: flex;
        flex-direction: column;
    }
    &__input {
        text-align: center;
    }
    &__input,
    &__textarea {
        padding: 5px 10px;
        margin: 0.5rem 0;
        border: none;
        border-radius: 4px;
        &:focus {
            outline: none;
            box-shadow: 0 0 0 0.2rem rgba(155,89,182,.5);
            border-color: transparent;
        }
    }
    &__submit {
        width: 150px;
        line-height: 3;
        margin: 0 auto;
        background: #8e44ad;
        font-size: 15px;
        border: none;
        color: #ecf0f1;
        border-radius: 4px;
        cursor: pointer;
        &:hover {
          background: #1abc9c;
        }
    }
}

@media all and (max-width: 840px) {
  .contact__container {
    flex-direction: column;
    align-items: center;
  }
}
</style>
