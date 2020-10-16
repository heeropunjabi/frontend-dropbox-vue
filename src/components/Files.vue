<template>
  <div class="container">
    <br>
    <h3>List of your Files</h3>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">Name</th>
          <th scope="col">Created_at</th>
          <th scope="col">Updated_at</th>
          <th scope="col">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="file in files" v-bind:key="file.name"> 
          <th scope="row">{{file.name}}</th>
          <td>{{file.createdAt}}</td>
          <td>{{file.updatedAt}}</td>
          <td><button class="btn btn-danger" @click="deleteFile(file.name)">Delete</button></td>
        </tr>
      </tbody>
    </table> 
  </div> 
</template>

<script>
import axios from 'axios';
export default {
  name: "Files",
  data() {
      return {
        files: [],
      };
    },
    created: function() {
      axios
        .get('http://localhost:3000/list')
        .then(res => {
          this.files = res.data;
        })
    },
    methods: {
      deleteFile(fileName) {
        axios.delete(`http://localhost:3000/${fileName}`).then(()=>{
          axios
        .get('http://localhost:3000/list')
        .then(res => {
          this.files = res.data;
        })

          });
    }
},
};
</script>

<style>
h3 {
  margin-top: 5%;
}
</style>
