<template>
  <form @submit.prevent="handleSubmit">
    <h1>Signup Form</h1>
    <label>Email:</label>
    <input type="email" required v-model="email" />
    <label>Pasword:</label>
    <input type="password" required v-model="password" />
    <div v-if="passwordError">{{ passwordError }}</div>
    <label>Role:</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>
    <div>
      <label>Skills:</label>
      <input type="text" v-model="tempSkill" @keyup="addSkill" />
      <div v-for="skill in skills" :key="skill">
        <span @click="removeSkill(skill)">{{ skill }}</span>
      </div>
    </div>
    <div>
      <label>Accept terms and conditions</label>
      <input type="checkbox" required v-model="terms" />
    </div>
    <div>
      <label>Mario</label>
      <input type="checkbox" value="Mario" v-model="names" />
    </div>
    <div>
      <label>Luigi</label>
      <input type="checkbox" value="Luigi" v-model="names" />
    </div>
    <div>
      <label>Yoshi</label>
      <input type="checkbox" value="Yoshi" v-model="names" />
    </div>
    <div class="submit">
      <button>Create an Account</button>
    </div>
  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
  <p>Terms Accepted: {{ terms }}</p>
  <p>Names: {{ names }}</p>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      role: "",
      terms: false,
      names: [],
      tempSkill: "",
      skills: [],
      passwordError: "",
    };
  },
  methods: {
    addSkill(event) {
      //   console.log(event)
      if (event.key === "," && this.tempSkill) {
        if (!this.skills.includes(this.tempSkill)) {
          this.skills.push(this.tempSkill);
        }
        this.tempSkill = "";
      }
    },
    removeSkill(skill) {
      this.skills = this.skills.filter((elem) => {
        return skill !== elem;
      });
    },
    handleSubmit() {
      // console.log(this.password)
      this.passwordError = this.password.length > 5 ? '' : 'password must be more than 5 characters'
      // if(this.password.length <= 5) {
      //   console.log('hit')
      //   return this.passwordError = 'password must be more than 5 characters'
      // } else {
      //   return this.passwordError = ''
      // }
      if(!this.passwordError) {
        console.log('form submitted')
      }
    },
  },
};
</script>

<style></style>
