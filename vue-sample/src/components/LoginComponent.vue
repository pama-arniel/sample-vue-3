<script >
export default {
  name: 'LoginComponent',
  data() {
    return{
        Name: "BRESA",
        Subtitle: 'SALES AND INVENTORY SYSTEM',
        formData: {
            username: '',
            password: ''
          },
        errorMessage: ''

    }
  },

  methods: {
    login() {
        if (this.formData.username === 'admin' && this.formData.password === 'password') {
           // do something
        } else {
            this.errorMessage = "Error: Invalid data entry"
        }
    }
  }
}
</script>

<template>
  <div id="app">
      <form @submit.prevent="login">
      <div class="Logo">
        <p id="Bresa">{{Name}}</p>
        <p id="SIP">{{Subtitle}}</p>
      </div>
      <br>
      <h2 id="login">LOGIN</h2>
      <input type="username" v-model="formData.username" required>
      <br>
      <input type="password" v-model="formData.password" required>
      <br>
      <p v-if="errorMessage" class="error-message">{{ errorMessage }}</p>
      <br>
      <button type="submit">LOGIN</button>
    </form>
  </div>
</template>

<style scope>
body{
    font-family: 'Inter', sans-serif;
    background-image: url(../assets/BG.jpg);
    background-size: cover;
    background-position: center;
}

form {
    width: 300px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    background: white;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 0px 0px 30px 30px;
    padding-top: 2px;
  }
  
  label {
    display: block;
    margin-bottom: 10px;
  }
  
  input {
    width: 100%;
    padding: 10px;
    margin-bottom: 20px;
    border: 0px solid #ccc;
    box-sizing: border-box;
    border-bottom: 2px solid black;
    font-style: italic;
  }

  button {
    background: #4CAF50;
    color: white;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    width: 100%;
    border-radius: 10px;
  }

  .Logo {
    text-align: center;
    margin: 0 auto;
    background: #F67F7F;
    line-height: 0px;
    width: 343px;
    position: absolute;
    margin-top: -179px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 30px 30px 0px 0px;
    font-family: 'Inter';
    border: 0px;
    border-bottom: 4px solid #4CAF50;
  }
  
  #Bresa{
    text-align: center;
    color: white;
    font-size: 40px;
    font-weight: bold;
    margin: 30px;
    text-shadow: -2px -2px 4px #000, 2px -2px 4px #000, -2px 2px 4px #000, 2px 2px 4px #000;
  }
  #SIP{
    text-align: center;
    font-style: italic;
    font-size: 15px;
    font-weight: bold;
  }

  #login{
    text-align: center;
    font-size: 30px;
  }

 .error-message{
  font-size: 15px;
  color: red;
 }
  
</style>