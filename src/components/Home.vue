<template>
  <div class="home">
    <section class="hero is-dark">
      
      <div class="hero-body">
        
        <div class="container">
          <h1 class="title">Just Music!</h1>
          <h2 class="subtitle">
             A place just for music!
          </h2>

          <SignUpForm v-if="this.display = false"></SignUpForm>

          <div class="button-block">

            <button class="button is-xl is-dark" @click="toggle()">
              Login
            </button>

            <button class="button is-xl is-dark">
              Sign Up
            </button>

          </div>

        </div>
      </div>
    </section>
  </div>
</template>



<script>
import SignUpForm from "../components/SignUpForm.vue"
  export default {
    name: 'LoginPage',
    components: {
      SignUpForm
    },  
    methods: {
      toggle(){
        this.display = false;
      }
    }
  };
</script>

<style lang="scss" scoped>
  .hero {
    text-align: center;
    background-image: "just_music_v2\src\assets\just-music-log(small).jpg";
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    height: 400px;
  }
  .hero-body .title {
    text-shadow: 4px 4px 4px rgba(0, 0, 0, 0.6);
    padding: 40px 0 20px 0;
    font-size: 60px;
  }
  .subtitle {
    text-shadow: 4px 4px 4px rgba(0, 0, 0, 0.7);
    font-size: 30px;
  }
  .button-block {
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    width: 100%;
    position: absolute;
    bottom: -150px;
    .button {
      margin-right: 50px;
      padding-left: 50px;
      padding-right: 50px;
    }
    .welcome {
      width: 400px;
      padding: 10px;
      margin-left: auto;
      margin-right: auto;
    }
  }
  .is-xl {
    font-size: 1.7rem;
  }
</style>