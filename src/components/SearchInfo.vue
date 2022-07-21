<script lang="ts" setup>
import { ref } from "@vue/reactivity";
import { defineEmits } from "vue";

const name = ref("");
const emit = defineEmits(["submit"]);

const submit = () => {
 if(name.value !== ''){
   emit("submit", name.value);
 }
};
</script>

<template>
  <div class="search">
    <input type="text" v-model="name" @keydown.enter="submit" />
    <button @click="submit">Search</button>
  </div>
</template>
<style lang="scss">
.search {
  display: flex;
  margin-top: 10px;
  input {
    width: 100%;
    height: 35px;
  }
  button {
    background-color: #f1f1f1;
    color: black;
    border: none;
    cursor: pointer;
    border-radius: 4px;
    margin-left: 5px;
    padding: 0px 4px;
  }
}
</style>
