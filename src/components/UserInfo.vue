<script lang="ts" setup>
import { reactive } from "@vue/runtime-core";
import axios from "axios";
import SearchInfo from "@/components/SearchInfo.vue";

interface info {
  name: string;
  age: number;
  count: string;
}
const data: info = reactive({
  name: "",
  age: 0,
  count: "",
});

const get = (name: string) => {
  axios.get(`https://api.agify.io/?name=${name}`).then((res) => {
    data.name = res.data.name;
    data.age = res.data.age;
    data.count = res.data.count;
    console.log(res.data);
  });
};
</script>

<template>
  <section>
    <div class="container">
      <div class="art_list">
        <ul>
          <h1>Predict age based on a name</h1>
          <!-- li -->
          <li>
            <!-- Serach  -->
            <SearchInfo @submit="get" />

            <!-- User İnfo  -->
            <div class="user-info">
              <span v-show="data.name">Name : {{ data.name }} </span>
              <span
                v-if="data.age == null || data.age == undefined"
                style="color: red"
                >You Are Giving Incorrect Information</span
              >
              <span v-show="data.age > 0">Age: {{ data.age }}</span>
              <span v-show="data.count">Posta Code: {{ data.count }}</span>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
ul {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  h1 {
    margin-bottom: 10px;
  }
  li {
    width: 300px;
    display: flex;
    flex-direction: column;

    .user-info {
      display: flex;
      flex-direction: column;
      justify-content: center;
      margin-top: 30px;
      span {
        font-size: 18px;
        font-weight: bold;
        margin-bottom: 10px;
      }
    }
  }
}
</style>
