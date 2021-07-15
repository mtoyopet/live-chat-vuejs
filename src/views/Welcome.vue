<template>
  <div class="container welcome">
    <p>ようこそ！</p>
    <!-- ここから追加する -->
    <LoginForm />
    <!-- ここまで追加する -->
  </div>
</template>

<script>
// ここから追加する
import LoginForm from '../components/LoginForm.vue'
export default {
  components: { LoginForm },
}
// ここまで追加する
</script>

<style>
  .welcome {
    text-align: center;
    padding: 20px 0;
  }

  /* ここから追加 */
  .welcome form {
    width: 300px;
    margin: 20px auto;
  }
  .welcome label {
    display: block;
    margin: 20px 0 10px;
  }
  .welcome input {
    width: 100%;
    padding: 12px 20px;
    margin: 8px auto;
    border-radius: 4px;
    border: 1px solid #eee;
    outline: none;
    box-sizing: border-box;
  }
  .welcome span{
    font-weight: bold;
    text-decoration: underline;
    cursor: pointer;
  }
  .welcome button {
    margin: 20px auto;
  }
  /* ここまで追加 */
</style>
