<template>
  <h2>アカウントを登録</h2>
  <form @submit.prevent="signUp">
    <input type="text" required placeholder="名前" v-model="name">
    <input type="email" required placeholder="メールアドレス" v-model="email">
    <input type="password" required placeholder="パスワード" v-model="password">
    <input type="password" required placeholder="パスワード（確認用）" v-model="passwordConfirmation">
    <!-- ======= ここから追加する ======= -->
    <div class="error">{{ error }}</div>
    <!-- ======= ここまで追加する ======= -->
    <button>登録する</button>
  </form>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      name: '',
      email: '',
      password: '',
      passwordConfirmation: '',
      // ======= ここから追加する =======
      error: null
      // ======= ここまで追加する =======
    }
  },
  methods: {
    async signUp () {
      // ======= ここから追加する =======
      this.error = null
      // ======= ここまで追加する =======
      try {
        const res = await axios.post('http://localhost:3000/auth', {
          name: this.name,
          email: this.email,
          password: this.password,
          password_confirmation: this.passwordConfirmation
          }
        )
        // ======= ここから追加する =======
        if (!res) {
          throw new Error('アカウントを登録できませんでした')
        }
        this.error = null
        // ======= ここから追加する =======
        return res
      } catch (error) {
        // ======= ここから追加する =======
        this.error = 'アカウントを登録できませんでした'
        // ======= ここから追加する =======
      }
    }
  }
}
</script>
