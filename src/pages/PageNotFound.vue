<template>
  <div class="col-full" :class="$style.centred">
    <h1 :class="$style.headingLarge">Not Found</h1>
    <p :class="$style.textLarge">Ooops, what are you fucking for something fucked up morons?
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

<style module>
.headingLarge {
  font-size: 100px;
}

.textLarge {
  font-size: 50px;
  font-weight: 100;
}

.centred {
  text-align: center;
}
</style>
