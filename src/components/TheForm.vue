`<template>
  <form @submit="submitForm">
    <div class="form-control">
      <label for="user-name">Your Name</label>
      <input id="user-name" name="user-name" type="text" v-model="userName" />
    </div>

    <div class="form-control">
      <label for="age">Your Age (Years)</label>
      <input id="age" name="age" type="number" v-model="userAge" />
    </div>

    <div class="form-control">
      <label for="referrer">How did you hear about us?</label>
      <select id="referrer" name="referrer" v-model="referrer">
        <option value="google">Google</option>
        <option value="wom">Word of mouth</option>
        <option value="newspaper">Newspaper</option>
      </select>
    </div>

    <div class="form-control">
      <h2>What are you interested in?</h2>
      <div>
        <input id="interest-news" name="interest" type="checkbox" />
        <label for="interest-news">News</label>
      </div>
      <div>
        <input id="interest-tutorials" name="interest" type="checkbox" />
        <label for="interest-tutorials">Tutorials</label>
      </div>
      <div>
        <input id="interest-nothing" name="interest" type="checkbox" />
        <label for="interest-nothing">Nothing</label>
      </div>
    </div>

    <div class="form-control">
      <h2>How do you learn?</h2>
      <div>
        <input id="how-video" name="how" type="radio" />
        <label for="how-video">Video Courses</label>
      </div>
      <div>
        <input id="how-blogs" name="how" type="radio" />
        <label for="how-blogs">Blogs</label>
      </div>
      <div>
        <input id="how-other" name="how" type="radio" />
        <label for="how-other">Other</label>
      </div>
    </div>

    <div>
      <button type="submit">Save Data</button>
    </div>
  </form>
</template>

<script>
export default {
  data(){
    return {
      userName: '',
      userAge: null,
      referrer: 'wom',
    };
  },

  methods: {
    submitForm(e){
    e.preventDefault();
    console.log(this.userName);
    this.userName= '';
    console.log(this.userAge);
    this.userAge= null;
    console.log(this.referrer);
    this.referrer='wom';
    }
  }
}
</script>

<style scoped>
form {
  @apply my-8 mx-auto max-w-2xl rounded-xl p-4 ;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  background-color: #ffffff;
}

.form-control {
  @apply my-6 mx-0
}

label {
  font-weight: bold;
}

h2 {
  @apply text-base my-2 mx-0 font-bold
}

input,
select {
  font: inherit;
  @apply block w-full  mt-2 py-1 px-2
}

input,
select{
  @apply border-solid border-2 border-blue-800;
}

select {
  width: auto;
}

input[type='checkbox'],
input[type='radio'] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}

input[type='checkbox'] + label,
input[type='radio'] + label {
  font-weight: normal;
}

button {
  font: inherit;
  border: 1px solid #0076bb;
  background-color: #0076bb;
  color: white;
  @apply py-1 px-4 rounded-xl cursor-pointer
}

button:hover,
button:active {
  border-color: #002350;
  background-color: #002350;
}
</style>