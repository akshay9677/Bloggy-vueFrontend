<template>

    <nav class="navbar navbar-light navbar-expand-lg  bg-success">
      <div class="container">
  <a class="navbar-brand" ><router-link class="links" to="/"><i class="fab fa-vuejs fa-lg"></i> Blogger</router-link></a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse " id="navbarSupportedContent">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
         <a class="nav-link"><router-link class="links" to="/">Home</router-link> </a>
      </li>
      <li class="nav-item">
       <a class="nav-link"> <router-link class="links" to="/compose"> Compose</router-link></a>
      </li>
      
      
    
    </ul>
    
  </div>
  </div>
</nav>
</template>

<script>
export default {
    name: "Navbar",
   
}
</script>
<style scoped>
.links{
    text-decoration: none;
    color: white;
}

</style>