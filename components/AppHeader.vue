<template>
<div class="container-fluid">
  <b-navbar toggleable="lg"   >
    <nuxtLink to="/" class="navbar-brand text-color ">EL-Gibbor</nuxtLink>


    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <nuxtLink to="/" class="navlink text-color">Home</nuxtLink>
        
         <b-nav-item-dropdown text="Classes" right class="text-color">
          <b-dropdown-item href="#">Pre Nursery</b-dropdown-item>
          <b-dropdown-item href="#">Nursery 1</b-dropdown-item>
          <b-dropdown-item href="#">Nursery 2</b-dropdown-item>
          <b-dropdown-item href="#">Transition</b-dropdown-item>
          <b-dropdown-item href="#">Primary 1</b-dropdown-item>
          <b-dropdown-item href="#">Primary 2</b-dropdown-item>
          <b-dropdown-item href="#">Primary 3</b-dropdown-item>
          <b-dropdown-item href="#">Primary 4</b-dropdown-item>
          <b-dropdown-item href="#">Primary 5</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>


        <b-navbar-nav class="m-auto text-center">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
        </b-nav-form>
        </b-navbar-nav>
      

      <b-navbar-nav class="ml-auto">
       <nuxtLink to="/register-student" class="navlink text-color">
          Add Student
       </nuxtLink>
        <b-nav-item-dropdown right class="text-color">
          <!-- Using 'button-content' slot -->
          <template #button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>

<script>
export default {
    
}
</script>


<style scoped>
.navlink {
  padding-right: 0.5rem;
  padding-left: 0.5rem;
  display: block;
  padding: 0.5rem 1rem;
  font-weight: 500;
  text-decoration: none;
}

.text-color {
  color: rgb(18, 18, 133);

}

.navbar-brand {
  font-weight: 500;
}

.navbar-light .navbar-nav .nav-link {
  color: rgb(18, 18, 133);

}
</style>