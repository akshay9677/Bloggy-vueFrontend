<template>
  <div class="about container"> 
    <h1 class="head">Blogger</h1>
    <div class="alert alert-success alertt" role="alert">
  A simple Blog Post App- Lorem ipsum dolor sit amet, consectetur adipiscing elit.
</div>
    <div v-bind:key="post.id" v-for="post of posts">
      <br>
      <h5><strong>{{post.title}}</strong></h5>
      <p>{{post.body}}</p>
      <button class="btn btn-danger btn-sm" v-on:click="handleClick(post._id)"><i class="far fa-window-close"></i> Delete</button>
      &nbsp;
      <button class="btn btn-primary btn-sm" v-on:click="handleClick2(post._id)"><i class="far fa-thumbs-up"></i> {{post.likes}} Like</button>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import swal from "sweetalert";
export default {
  data () {
    return {
      posts: []
    }
  },
  mounted () {
    axios
      .get('http://localhost:5000/blogs')
      .then(response => {this.posts = response.data;console.log(response.data[0]._id)})

      
  },
  methods :{
    handleClick(id){
      

      swal({
  title: "Are you sure?",
  text: "Once deleted, you will not be able to recover the post",
  icon: "warning",
  buttons: true,
  dangerMode: true,
})
.then((willDelete) => {
  if (willDelete) {
     axios
      .delete('http://localhost:5000/blogs/'+id)
       window.location = "/";
  } else {
    swal("Your post is not deleted");
  }
});
          
      

     
      
    },
    handleClick2(id){
      axios
      .put('http://localhost:5000/blogs/'+id)

      window.location = "/"
    }
  }
}
</script>

<style scoped>
.about{
  text-align: left;
}
.head{
  text-align: center;
  margin-bottom: 10px;
}
.alertt{
  text-align: center;
}
</style>
