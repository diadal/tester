<template>
  <q-page class="row items-center justify-evenly">
   <q-btn label="Take Picture" @click="takePicture"/>
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { Camera, CameraResultType } from '@capacitor/camera';

export default defineComponent({
  name: 'IndexPage',
  setup () {

     const takePicture = async () => {
       const image = await Camera.getPhoto({
            quality: 90,
            allowEditing: true,
            resultType: CameraResultType.Uri,
          });
          const imageUrl = image.webPath;
          console.log('imageUrl: ', imageUrl);
    };

    return {
takePicture

     };
  }
});
</script>
