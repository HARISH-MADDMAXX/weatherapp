<template>
  <header class="position-sticky shadow  mb-5 bg-body rounded-3">
    <nav class="container-fluid bg-dark opacity-75 mt-2 rounded-3">
      <div class="row mx-auto">

        <div class="col">

          <RouterLink :to="{ name: 'home' }" style="text-decoration:none">

            <div class="d-inline-flex align-items-center">
              <div class="flex-shrink-0">
                <i class="fa-solid fa-sun fa-2xl text-info" style="position: relative; left:30%"></i>
              </div>
              <div class="flex-grow-1 ms-3 mt-1">
                <p class="text-info mt-2 fs-3">Local weather</p>

              </div>

            </div>
          </RouterLink>
        </div>
        <div class="col">
          <div class="d-flex flex-row-reverse">
            <i class="fa-sharp fa-solid fa-circle-info fa-xl text-info mt-4 ms-2" @click="toggleModal"></i>
           
              <i class="fa-solid fa-plus fa-xl text-info mt-4 ms-2"></i>
        
           
          </div>
        </div>



      </div>
      <BaseModal :modalActive = "modalActive" @close-modal="toggleModal">

        <div class="text-black">
          <h1 class="text-2xl mb-1">About:</h1>
          <p class="mb-4">
            The Local Weather allows you to track the current and
            future weather of cities of your choosing.
          </p>
          <h2 class="text-2xl">How it works:</h2>
         <div class="text-start">
         
          <ol class="list-decimal list-inside mb-4">
            <li>
              Search for your city by entering the name into the
              search bar.
            </li>
            <li>
              Select a city within the results, this will take
              you to the current weather for your selection.
            </li>
            <li>
              Track the city by clicking on the "+" icon in the
              top right. This will save the city to view at a
              later time on the home page.
            </li>
          </ol>
         
         </div>

          <h2 class="text-2xl">Removing a city</h2>
          <p>
            If you no longer wish to track a city, simply select
            the city within the home page. At the bottom of the
            page, there will be am option to delete the city.
          </p>
        </div> 

 
      </BaseModal>

    </nav>

  </header>
</template>

<script setup>

import { RouterLink } from 'vue-router';
import { ref } from 'vue';

import BaseModal from './BaseModal.vue';

const modalActive = ref(null);
const toggleModal = () => {
  modalActive.value = !modalActive.value
}
</script>


