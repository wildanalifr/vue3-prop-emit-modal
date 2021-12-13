<script>
import { ref } from "vue";
import ButtonRepo from "@/components/ButtonRepo.vue";
import Modal from "@/components/Modal.vue";
import Alert from "@/components/Alert.vue";

export default {
  components: {
    ButtonRepo,
    Modal,
    Alert,
  },

  setup() {
    let ok = ref(false);
    const clickOk = () => {
      ok.value = !ok.value;
    };

    const emitMethod = (value) => {
      ok.value = value;
    };

    return {
      ok,
      clickOk,
      emitMethod,
    };
  },
};
</script>

<template>
  <div class="bg-gray-50">
    <div class="max-w-screen-xl px-4 py-12 mx-auto sm:px-6 lg:py-16 lg:px-8 lg:flex lg:items-center lg:justify-between">
      <h2 class="text-3xl font-extrabold leading-9 tracking-tight text-gray-900 sm:text-4xl sm:leading-10">
        Ready to dive in?
        <br />
        <span class="text-indigo-600">Vite + Vue 3 + Tailwind CSS</span>
      </h2>
      <!-- <Alert :halo="ok" /> -->
      <div class="flex mt-8 lg:flex-shrink-0 lg:mt-0 gap-x-3">
        <div class="inline-flex rounded-md shadow">
          <button @click="clickOk" class="inline-flex items-center justify-center px-5 py-3 text-base font-medium leading-6 text-white transition duration-150 ease-in-out bg-amber-600 border border-transparent rounded-md hover:bg-amber-500 focus:outline-none">Modal</button>
        </div>
        <div class="inline-flex rounded-md shadow">
          <router-link to="/about" class="inline-flex items-center justify-center px-5 py-3 text-base font-medium leading-6 text-white transition duration-150 ease-in-out bg-indigo-600 border border-transparent rounded-md hover:bg-indigo-500 focus:outline-none">Next Page</router-link>
        </div>
        <ButtonRepo />
      </div>
    </div>
    <Modal :open="ok" @emitModal="emitMethod" />
  </div>
</template>
