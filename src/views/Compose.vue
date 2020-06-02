<template>

  <div class="card border-dark mb-3 container" style="width: 30rem;">
      <div>
       <h1>Compose</h1>
      </div>
  <div class="card-body ">
    <form @submit="addTodo">
  <div class="form-group">
    <label >Title</label>
    <input type="text" v-model="title" class="form-control form-control-lg" placeholder="Enter Title" name="title"> 
  </div>
  <div class="form-group">
    <label for="exampleFormControlTextarea1">Body</label>
    <textarea class="form-control form-control-lg" v-model="body" id="exampleFormControlTextarea1" rows="5" placeholder="Enter Post" name="body"></textarea>
  </div>
  <button type="submit" class="btn btn-dark" >Submit</button>
</form>
  </div>
</div>
</template>


<script>
import axios from "axios";
import swal from "sweetalert";
export default {
    data(){
       return{
        title: "",
        body: ""
    }
    },
    
    methods: {
        addTodo(){
          swal({
                 title: "Good job!",
                 icon: "success",
                })
            const newBlog ={
                title: this.title,
                body: this.body
            }
            
            axios.post("http://localhost:5000/blogs/add",newBlog)
         .then(res => console.log(res.data));
        

         window.location = "/";

        
        }
    }
}
</script>