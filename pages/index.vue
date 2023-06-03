<template>
  <div>
    <MainSection title="Главная" :loading="loading">
      <Head>
        <Title>Home / Twitter</Title>
      </Head>
     <div class="p-4">
       {{ response }}
     </div>
    </MainSection>
  </div>
</template>

<script setup lang="ts">

import axios from 'axios'

const options = {
  method: 'GET',
  url: 'https://jsonplaceholder.typicode.com/todos',
};

const loading = ref(false)
const response = ref()
onBeforeMount(async () => {
  loading.value = true
  try {
    response.value = await axios.request(options);
    console.log(response.value.data);
  } catch (error) {
    console.error(error);
  } finally {
    loading.value = false
  }
})

</script>