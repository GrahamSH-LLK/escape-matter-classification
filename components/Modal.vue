<template>
  <vue-final-modal
    v-slot="{ params, close }"
    :lock-scroll="false"
    :drag="true"
    dragSelector="#modal-header"
    :resize="true"
    v-bind="$attrs"
    classes="flex justify-center items-center"
    content-class="relative flex flex-col max-h-full mx-4  w-full h-full md:w-1/2 md:h-1/2"
    v-on="$listeners"
  >
    <span
      class="mr-8 w-full bg-gray-600 text-white p-2 font-semibold cursor-move"
      id="modal-header"
    >
      <slot name="title"></slot>
    </span>
    <div
      class="flex-grow overflow-y-auto bg-white p-2 flex flex-col bg-gray-700"
    >
      <div class="flex-1 mb-auto">
        <slot v-bind:params="params"></slot>
      </div>
      <div class="mt-auto" v-if="showButtons">
        <button
          class="
            bg-red-500
            text-white text-center
            font-bold
            mt-2
            p-2
            h-10
            cursor-pointer
          "
          @click="$emit('confirm', close)"
        >
          Submit
        </button>
        <button @click="$emit('cancel', close)">Cancel</button>
      </div>
    </div>
    <button class="absolute top-0 right-0 mt-2 mr-2 text-white" @click="close">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-6 w-6"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M6 18L18 6M6 6l12 12"
        />
      </svg>
    </button>
  </vue-final-modal>
</template>

<script>
export default {
  props: ['showButtons'],
}
// h-5 w-5
// Force jit to add those classes
</script>
