<template>
    

<v-sheet
  class="d-flex justify-center align-center absolute rounded-lg ms-4 mt-n8"
  :color="color"
  elevation="24"
  height="64"
  rounded
  width="64"
>
<v-icon   color="white" dense>
    {{icon}}
</v-icon>
</v-sheet>
</template>





 
<script>
export default {
 props: ['icon','color']
}
</script>