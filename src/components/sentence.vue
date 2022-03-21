<template>
    <h2>Please register your information </h2>
    <form @submit.prevent= handleSubmit()>
        <label>Full Name:</label>
        <input type="name" required v-model="name">
        <label>Email:</label>
        <input type="email" required v-model="email">
        <label>Password:</label>
        <input type="password" required v-model="password">
        <div v-if="passwordError" class="error">{{ passwordError }}</div>    
        <label>Role: </label>
        <select v-model="role">
            <option value="FrontEnd">FrontEnd</option>
            <option value="BackEnd">BackEnd</option>
            <option value="Webdesign">Web Design</option>
        </select>
        <div v-if = "role === 'FrontEnd'">
            <p>What do you work with?</p>
            <select v-model="workwith">
                <option value="Vue">Vue.JS</option>
                <option value="React">React</option>
                <option value="Angular">Angular</option>
                <option value="Flutter">Flutter</option>
            </select>
        </div>    
        <div v-if= "role === 'BackEnd'">
            <p>What do you work with?</p>
            <select v-model="workwith">
                <option value="Python">Python</option>
                <option value="PHP">PHP</option>
                <option value="Java">Java</option>
                <option value="C++">C++</option>
            </select>
        </div>    
        <div v-if= "role === 'Webdesign'">
            <p>What do you work with?</p>
            <select v-model="workwith">
                <option value="Bootstrap">Bootstrap</option>
                <option value="Tailwind">Tailwind</option>
                <option value="Materialize">Materialize</option>
            </select>    
        </div>
        <label>Skills</label>
        <input type="text" v-model="eachSkill" @keyup="addSkill">
        <div v-for ="skill in skills" :key="skill" class="pill">
            <span @click="deleteSkill(skill)">{{skill}}</span>
        </div>
        <br>
        <small v-if="skills !== []" @click="deleteSkill2()">Click here to clear</small>
        <div type="terms">
            <input class="checkbox" @click="acceptterms()" type="checkbox" required> 
            <label>I accept the terms and conditions</label>  
        </div>    
        <div class="submit">
        <button v-if="terms === true">Create and account</button>
        </div>

    </form>
    <p>{{name}}</p>
    <p>{{email}}</p>
    <p>{{password}}</p>
    <p>{{role}}  {{workwith}}</p>
    <p v-if = "terms === true">Terms have been accepted</p>
</template>

<script>
export default {
      data(){
          return{
              name: '',
              email:'',
              password:'',
              role: '',
              workwith:'',
              terms: false,
              eachSkill: '',
              skills: [],
              passwordError: ''

          }
      },
      methods:{
          acceptterms(){
              this.terms = !this.terms;
          },     
          addSkill(e){
              if (e.key === 'Enter' && this.eachSkill){
                if (!this.skills.includes(this.eachSkill)){
                  this.skills.push(this.eachSkill)
                }
              this.eachSkill = ''
              }
          },
         deleteSkill(skill) {
             this.skills = this.skills.filter((item) => {
                return skill !== item
             })
         },
         deleteSkill2() {
             this.skills = []

         },
         handleSubmit() {
             this.passwordError = this.password.length > 5 ?
              '' : 'Password must be at least 6 characters long'

              if(!this.passwordError) {
                  console.log ('name:', this.name)
                  console.log ('email:', this.email)
                  console.log ('password:', this.password)
                  console.log ('role:', this.role)
                  console.log ('workwith', this.workwith)
                  console.log ('skills', this.skills)
              }
         }
          
      } 
}
</script>

<style scoped>
form{
    max-width:420px;
    margin: 30px auto;
    background: rgb(255, 255, 255);
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}
label{
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0,6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input, select{
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
}
.checkbox {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
}
button{
    font-size: 25px;
    align-content: center;
    background-color:rgb(3, 177, 119);
    border-radius: 10px;
    margin-top: 20px;
    padding: 10px 20px;
    text-align: center;
    margin-left: 2cm;
}
button:hover{
    background-color: rgb(216, 236, 230);
}
.pill{
    display:inline-block;
    margin: 20px 10px 0 0;
    padding: 6px 12px;
    background-color: rgb(30, 40, 58);
    border-radius: 15px;
    font-size: 14px;
    letter-spacing: 1px;
    cursor: pointer;
    color: white;
}
</style>