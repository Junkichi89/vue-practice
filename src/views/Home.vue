<template>
  <div class="home">
    <button @click="entry">出社</button>
    <button @click="leave">退社</button>
    <ul>
      <li v-for="(data, index) in datas.data" :key="index">
        {{ data }} | {{ index }}
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import { reactive } from "vue";

export default {
  setup() {
    const datas = reactive<{ data: { [key: string]: string } }>({ data: {} });
    const entry = function() {
      datas.data[Date().toString()] = "出社";
    };

    const leave = function() {
      datas.data[Date().toString()] = "退社";
    };

    return { 
      datas, entry, leave
    }
  },
};
</script>
