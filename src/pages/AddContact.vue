<template>
  <div>
     <h1>Add-contacts</h1>
       <form class="form-inline" action="/action_page.php">
          <div class="form-group">
            <label for="email">Email address:</label>
            <input type="email" class="form-control" id="email">
          </div>
          <div class="form-group">
            <label for="pwd">Password:</label>
            <input type="password" class="form-control" id="pwd">
          </div>
          <div class="checkbox">
            <label><input type="checkbox"> Remember me</label>
          </div>
          <button type="submit" class="btn btn-default">Submit</button>
      </form>
  </div>
</template>

<script>
export default {

 
}
</script>

<style>

</style>
