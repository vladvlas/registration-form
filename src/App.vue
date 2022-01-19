<template>
  <div class="app">
    <div class="wrapper">
      <form @submit.prevent class="form">
        <h2 class="title">Create account</h2>
        <p class="descr">Enter your email, password below and nickname</p>
        
        <label class="label" for="">email</label>
        <my-input 
          v-bind:value="email"
          @input="email = $event.target.value"
          class="input" type="email"
          placeholder="Email"
        />

        <label class="label" for="">password</label>
        <my-input 
          v-bind:value="password" 
          @input="password = $event.target.value"
          class="input" type="password" 
          placeholder="Password" 
        />

        <label class="label" for="">nickname</label>
        <my-input
          v-bind:value="name" 
          @input="name = $event.target.value"
          class="input" type="text" 
          placeholder="Nickname" 
        />
        <my-button @click="sendData" >
          Create
        </my-button>
      </form>
    </div>
  </div>
</template>

<script>
import MyButton from './UI/MyButton.vue';
import MyInput from './UI/MyInput.vue';
import axios from 'axios'

export default {
  components: { MyButton, MyInput },
  data() {
    return {
      email: '',
      password: '',
      name: ''
    };
  },
  methods: {
    sendData() {
      const newUser = {
        email: this.email,
        password: this.email,
        name: this.name
      }
      this.email = '',
      this.password = '',
      this.name = '',
      console.log(newUser)
      const jsrt = JSON.stringify(newUser);
      console.log(jsrt)
      async function fetchData() {
      try {
        const response = await axios.post('https://jsonplaceholder.typicode.com/posts?_limit=10')
        console.log(response)
      } catch (error) {
        alert('Error!')
      }
    }
    fetchData()
    },
    
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Mulish:wght@400;700&display=swap');
* {
  font-family: 'Mulish', sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.app {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100vh;
  background-color: #363740;
}
.wrapper {
  display: flex;
  justify-content: center;
  padding: 25px 0;
  background-color: #fff;
  max-width: 380px;
  width: 100%;
  height: 500px;
  border-radius: 8px;
}

.title {
  margin-top: 57px;
  margin-bottom: 18px;
  font-weight: bold;
  font-size: 24px;
  line-height: 30px;
  letter-spacing: 0.3px;
  text-align: center;
  color: #212121;
}

.descr {
  margin-bottom: 18px;
  font-weight: normal;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  letter-spacing: 0.3px;
  color: #9FA2B4;
}
.label {
  display: block;
  margin-bottom: 6px;
  font-weight: bold;
  font-size: 12px;
  line-height: 15px;
  letter-spacing: 0.3px;
  text-transform: uppercase;
  color: #9FA2B4;
}


</style>