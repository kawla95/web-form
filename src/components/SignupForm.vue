<template>
  <form @submit.prevent="handleSubmit"> 
    <label> First Name </label>
    <input type="firstName" required v-model="firstName">
    <label> Last Name </label>
    <input type="lastName" required v-model="lastName">
    <label> Email: </label>
    <input type="email" required v-model="email">
    <label> Role: </label>
    <select v-model="role"> 
        <option value="developer"> Web Developer</option>
        <option value="designer"> Web Designer</option>
    </select>
    <div class="terms">
        <input type="checkbox" v-model="terms" required>
        <label> Accept terms and conditions</label>
    </div>
    <div class="submit">
        <button> Create an Account </button>
    </div>
  </form>
  <p> First Name: {{ firstName }}</p>
  <p> Last Name: {{ lastName }}</p>
  <p> Email: {{ email }}</p>
  <p>Role: {{ role }}</p>
  <p> Terms accepted: {{ terms }}</p>



</template>

<script>

export default{
    data() {
        return {
            email: '',
            password: '',
            role: '', 
            terms: false,
            passwordError: "",
        }
        },
        methods: {
            handleSubmit() {
                //validate password
                this.passwordError = this.password.length >5 ? '' 
                :'Password must be atleast 6 characters long'

                if (!this.passwordError) {
                    console.log('email: ', this.email)
                    console.log('password: ', this.password)
                    console.log('role ', this.role)
                    console.log ('terms accepted: ', this.terms)
                }

            }
        }

}

</script>

<style>
form {
    max-width: 420px; 
    margin: 30px auto; 
    background: white; 
    text-align: left; 
    padding: 40px; 
    border-radius: 10px; 
}
label {
    color: #aaa; 
    display: inline-block; 
    margin: 25px 0 15px; 
    font-size: 0.6rem; 
    text-transform: uppercase; 
    letter-spacing: 1px; 
    font-weight: bold; 
}
input, select {
    display: block; 
    padding: 10px 6px; 
    width: 100%; 
    box-sizing: border-box; 
    border: none; 
    border-bottom: 1px solid #ddd;
    color: #555;
}
input[type='checkbox'] {
    display: inline-block; 
    width: 16px; 
    margin: 0 10px 0 0; 
    position: relative; 
    top: 2px; 

}
button {
    background: #0b6dff;
    border: 0;
    padding: 10px 20px; 
    margin-top: 20px; 
    color: white; 
    border-radius: 20px; 
}
.submit {
    text-align: center; 
}
.error {
    color: red; 
    margin-top: 10px; 
    font-size: 0.8em; 
    font-weight: bold; 
}

</style>