<script lang="ts">
import { defineComponent } from "vue";
import ButtonDistress from "./ButtonDistress.vue";
import DeviceScreen from "./DeviceScreen.vue";

export default defineComponent({
  methods: {
    emit(eventName: string) {
      document.dispatchEvent(new Event(eventName));
    }
  },
  components: { ButtonDistress, DeviceScreen }
});
</script>

<template>
  <div class="w-800px h-300px m-auto p-4 border-1 border-black rounded-xl">
    <div class="h-full flex space-x-4">
      <div class="w-1/4 flex flex-col items-center">
        <div class="grow-1 h-full"></div>
        <ButtonDistress class="ml-auto mr-2 h-20 w-20 bg-red text-white" />
      </div>

      <div class="h-full w-400px flex flex-col">
        <DeviceScreen class=" w-400px h-194px bg-orange" />
        <div class="h-12 flex justify-between items-end">
          <button class="w-12 h-8">---</button>
          <button class="w-12 h-8">---</button>
          <button class="w-12 h-8">---</button>
          <button class="w-12 h-8">---</button>
        </div>
      </div>

      <div class="h-full w-1/4 flex flex-col">
        <div class="w-full h-8 my-2 flex">
          <button class="mx-auto w-9">▲</button>
        </div>
        <div class="w-full h-8 my-2 flex justify-around">
          <button @click="emit('buttonLeft')" class="w-9">◀</button>
          <button class="w-10 text-xs tracking-tighter">ENT</button>
          <button class="w-9">▶</button>
        </div>
        <div class="w-full h-8 my-2 flex justify-around">
          <button class="w-12 text-xs tracking-tighter">MENU</button>
          <button @click="emit('buttonDown')" class="w-9">▼</button>
          <button class="w-12 text-xs tracking-tighter">CLR</button>
        </div>
        <div class="w-full h-full flex items-center">
          <button class="w-10 h-10 ml-4 mr-auto rounded-full bg-blue text-white text-xs">16/C</button>
          <button class="w-20 h-20 rounded-full">Power</button>
        </div>
      </div>
    </div>  </div>
</template>