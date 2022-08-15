<template>
  <img class="image" alt="Vue logo" src="./assets/logo.png">
  <h1>Vue Form</h1>
  <div>
    <pre>
      {{ JSON.stringify(formData, null, 2) }}
    </pre>
  </div>
  <form @submit="submitForm">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model="formData.name">
    </div>
    <div>
      <label for="profile">Profile Summory</label>
      <textarea id="profile" v-model="formData.profile"></textarea>
    </div>

    <div>
      <label>Country</label>
      <select id="country" v-model="formData.country">
        <option value="">Select a Country</option>
        <option value="india">India</option>
        <option value="Algeria">Algeria</option>
        <option value="Argentina">Argentina</option>
        <option value="Bahrain">Bahrain</option>
        <option value="Belgium">Belgium</option>
      </select>
    </div><br>

    <div>
      <label>Job Location</label>
      <select id="location" multiple v-model="formData.location">

        <option value="Kerala">Kerala</option>
        <option value="Karnataka">Karnataka</option>
        <option value="Andra">Andra</option>
        <option value="Maharashtra">Maharashtra</option>
        <option value="Goa">Goa</option>
      </select>
    </div><br>
    <div>
      <input type="checkbox" id="remote" v-model="formData.remoteWork">
      <label for="remote">Available for Remote</label>
    </div>
    

    <div>
      <label>Skill Set</label>
      <input type="checkbox" id="javascript" value="javascript" v-model="formData.skillSet">
      <label for="jc">JAVASCRIPT</label>
      <input type="checkbox" id="html" value="html" v-model="formData.skillSet">
      <label for="html">HTML</label>
      <input type="checkbox" id="css" value="css" v-model="formData.skillSet">
      <label for="css">CSS</label>
    </div>

    <div>
      <label>Years Of Experience</label>
      <input type="radio" id="0-2" value="0-2" v-model="formData.yearsOfExperience">
      <label for="0-2">0-2</label>
      <input type="radio" id="2-5" value="2-5" v-model="formData.yearsOfExperience">
      <label for="2-5">2-5</label>
      <input type="radio" id="5-10" value="5-10" v-model="formData.yearsOfExperience">
      <label for="5-10">5-10</label>
    </div>
    <div>
      <button>Summit</button>
    </div>

  </form>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      formData: {
        name: '',
        profile: '',
        country: '',
        location: [],
        remoteWork: false,
        skillSet: [],
        yearsOfExperience: ''
      }
    }
  },
  methods: {
    submitForm(event) {
      event.preventDefault()
      console.log("formValue", this.formData)
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 20px;
}

.image {
  margin-left: 600px;
}

label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input+label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
</style>
