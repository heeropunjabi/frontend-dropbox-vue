<template>
  <div >
    <h3> Upload File</h3>
    <form action="http://localhost:3000/upload" method="post" enctype="multipart/form-data">
  <input type="file" name="sampleFile">
  <input type="submit" value="upload" class="btn btn-primary">
  </form>
  </div> 
</template>

<script>
// import axios from 'axios';
export default {
  name: "Upload",
  
};
</script>