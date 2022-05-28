<template>
  <div class="login grid place-items-center p-10">
    <img src="../assets/just-music-log(small).jpg" alt="Just Music Logo" loading="lazy" />
    <div class="flex items-center">
    
   <section>
    <div class="field">
        <input class="input" type="username" placeholder="Enter Your Username Here">
    </div>

    <div class="field">
        <p class="control has-icons-left has-icons-right">
            <input class="input" type="email" placeholder="Email">
            <span class="icon is-small is-left">
            <i class="fas fa-envelope"></i>
            </span>
            <span class="icon is-small is-right">
            <i class="fas fa-check"></i>
            </span>
        </p>

        <div class="field">
            <p class="control has-icons-left">
                <input class="input" type="password" placeholder="Password">
                <span class="icon is-small is-left">
                <i class="fas fa-lock"></i>
                </span>
            </p>
        </div>

         <div class="field">
            <p class="control has-icons-left">
                <input class="input" type="confirm-password" placeholder="Confirm password">
                <span class="icon is-small is-left">
                <i class="fas fa-lock"></i>
                </span>
            </p>
        </div>

    </div>
</section>

     

      
    </div>
  </div>
</template>

<script>
import { auth, provider } from "../firebase";
import { CometChat } from "@cometchat-pro/chat";
import { cometChatConfig } from "../app.config";
import { ref } from "vue";
import { useRouter } from "vue-router";
import SignUpForm from '../components/SignUpForm.vue';
export default {
  name: "signup",
  setup() {
    SignUpForm
    let loading = ref(false);
    const router = useRouter();
    const signIn = () => {
      loading.value = true;
      auth
        .signInWithPopup(provider)
        .then((res) => loginCometChat(res.user))
        .catch((error) => {
          loading.value = false;
          console.log(error);
          alert(error.message);
        });
    };
   


    const signUpWithCometChat = (data) => {
      const authKey = cometChatConfig.AUTH_KEY;
      const user = new CometChat.User(data.uid);
      user.setName(data.displayName);
      user.setAvatar(data.photoURL);
      CometChat.createUser(user, authKey)
        .then(() => {
          loading.value = false;
          alert("You are now signed up, click the button again to login");
        })
        .catch((error) => {
          console.log(error);
          loading.value = false;
          alert(error.message);
        });
    };
    return { loading, signIn };
  }
};
</script>

<style scoped>
.login > img {
  object-fit: contain;
  width: 200px;
  height: 200px;
}
.login > div > button:first-child {
  border: 1px solid #45619d;
  background-color: #45619d;
  transition: all 0.3s ease-in-out;
  margin: 20px 5px;
}
.login > div > button:first-child:hover {
  background-color: transparent;
  color: #45619d;
}
/* .login > div > button:last-child {
  border: 1px solid #0a8d48;
  background-color: #0a8d48;
  transition: all 0.3s ease-in-out;
  margin: 20px 5px
}
.login > div > button:last-child:hover {
  background-color: transparent;
  color: #0a8d48;
} */
</style>