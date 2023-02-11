<template>
<Transition name="modal-outer">
  <div  
v-show ="modalActive"

 class="position-absolute text-center mt-2 bg-light ms-5 justify-content-center p-2">
<Transition name="modal-inner" >
<div v-if="modalActive" class="p-2 bg-light ">



<slot />
<button type="button" class="btn btn-outline-info"
@click="$emit('close-modal')"
>close</button>

</div>
</Transition>


</div>



</Transition>

</template>

<script setup>

defineEmits(['close-modal'])

defineProps({
  modalActive :{
    type :Boolean,
    default:false,
  },
})

</script>


