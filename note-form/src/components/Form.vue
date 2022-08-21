<template>
  <div class="container mt-5">
    <h1 class="mt-4 mb-4" style="textAlign:center">My First Mini Project Vue</h1>
    <form>
        <h3>Create Note</h3>
      <div class="form-group">
        <label for="title">Title</label>
        <input v-model="formData.title" type="text" id="title" class="form-control" />
      </div>
      <div class="form-group">
        <label for="text">Text</label>
        <textarea v-model="formData.text" id="text" class="form-control"></textarea>
      </div>
      <h3 class="mt-2">Country</h3>
      <select v-model="formData.select">
        <option
          v-bind:key="index"
          v-for="(country, index) in formData.listCountries"
        >
          {{ country }}
        </option>
      </select>

      <br /><br />
      <div class="form-check">
       <input v-model="formData.checkGender" value="woman" id="woman" type="checkbox" class="form-check-input">
       <label for="woman">Woman</label>
      </div>
      <div class="form-check">
       <input v-model="formData.checkGender" value="man" id="man" type="checkbox" class="form-check-input">
       <label for="man">Man</label>
      </div>
      
      <button @click.prevent="envoiInfos" class="btn btn-primary mt-4"> Submit </button>
    </form>

  <div v-if="infoSubmit">
    <h2>Reasults</h2>
   <div class="card p-3">
    <p > Title :{{formData.title}}</p>
    <p style="White-space: pre">Text : {{formData.text}}</p>
    <p>Gender:</p>
    <ul >
        <li v-bind:key="index" v-for="(gender,index) in formData.checkGender">{{gender}}</li>
    </ul>
    
    <p>Country:{{formData.select}}</p>
   </div>
   </div>
  </div>
</template>


<script>
export default {
  name: "form-vue",
  data() {
    return {
      formData: {
        title: "",
        text: "",
        checkGender: [],
        select: "",
        listCountries: ["France", "Italy", "Canada", "Japan"],
      },
      infoSubmit:false
    };
  },
  methods:{
    envoiInfos: function(){
   this.infoSubmit= true
    }
  }
};
</script>



<style scoped>
ul{
    list-style-type: none;
}
</style>