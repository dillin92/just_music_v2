<template>

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
</template>

<script>
  export default {
    name: 'SignUpForm'
  };
</script>