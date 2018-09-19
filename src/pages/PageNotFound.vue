<template>
  <div class="col-full">
    <h1>Not Found</h1>
    <p>Ooops, what are you fucking for something fucked up morons?
      <router-link :to="{name: 'Home'}">
        Kill em all!
      </router-link>
    </p>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
h1 {
  font-size: 100px;
}

p {
  font-size: 50px;
  font-weight: 100;
}

div {
  text-align: center;
}
</style>
