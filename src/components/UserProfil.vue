<template>
  <div class ="flex border px-4 py-2 max-w-300 mx-auto my-2">
    <div class="text-center">
      <p>{{ user.name }}</p>
      <h2>{{ user.email }} {{ user.password }}</h2>
    </div>
    <button class="absolute  right-2 bg-red-500 w-40 rounded text-white ml-auto py-3 px-6 border rounded-sm">Delete</button>
  </div>
</template>

<script>
export default {
  props:{
    user:{
      type:Object,
      required: true
    }
  }
}
</script>

<style>

</style>