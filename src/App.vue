<template>
  <div class="app">
    <input
      v-model="user.phone"
      placeholder="phone"
    />
<!--    <button class="brn btn-primary" @click="getCode">GET_CODE</button>-->
    <input
      v-model="user.code"
      placeholder="code"
    />
<!--    <button class="brn btn-secondary" @click="getToken">GET_TOKEN</button>-->
    <button class="brn btn-secondary" @click="setToken">SET_TOKEN</button>

  </div>
</template>
<script>
import SDK, {KeStrategy} from "@market-tech/frontend-auth-sdk"


const AuthSDK = new SDK(
  KeStrategy.getInstance()
    .getOptionsBuilder()
    .setAuthEndpoint("https://api.dev.cluster.kznexpess.com/api")
    .getStrategy()
)

export default {
  beforeCreate() {
    AuthSDK.getTokenStream().subscribe(
      (token) => {
        console.log("TEST_APP", token)
      }
    )
  },
  data() {
    return {
      user: {
        phone: "9652557006",
        code: null
      },
    }
  },

  methods: {
    async getCode(){
      // try {
      //   const data = await auth.signInByPhone(this.$data.user.phone)
      //   console.log(data);
      // } catch (e) {
      //   console.log(e);
      // }
    },
    async setToken(){
      try {
        await KeStrategy.setToken("my token: 123")
      } catch (e) {
        console.log(e);
      }
    }
  }

}
</script>
<style>
* {
  margin: 0;
  box-sizing: border-box;
  padding: 0px;
}


.app {
  padding: 20px;
}

.app form {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-content: center;
  gap: 16px;
}

.app input {
  width: 100%;

}
</style>
