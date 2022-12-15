<template>
  <q-page class="column flex-center q-pa-md">
    <q-card
      class="q-pa-xs full-height"
      fill
      full-height
      style="width: 100%; height: 100%"
    >
      <div class="row">
        <div class="col-4 q-pa-xs">
          <q-card fill flat bordered>
            <q-card-section>
              <div class="text-h6">Our Changing Planet</div>
            </q-card-section>

            <q-card-section class="q-pt-none">
              <fileList />
            </q-card-section>
          </q-card>
        </div>
        <div class="col-8 column">
          <div class="col-8 q-pa-xs">
            <q-card flat bordered>
              <q-card-section>
                <div class="text-h6">Our Changing Planet</div>
              </q-card-section>

              <q-card-section class="q-pt-none">
                <modelViewer />
              </q-card-section>
            </q-card>
          </div>
          <div class="col-4 q-pa-xs">
            <q-card flat bordered>
              <q-card-section>
                <div class="text-h6">Our Changing Planet</div>
              </q-card-section>

              <q-card-section class="q-pt-none">
                <imageViewer />
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import fileList from '../components/fileList.vue';
import modelViewer from '../components/modelViewer.vue';
import imageViewer from '../components/imageViewer.vue';
export default defineComponent({
  components: { fileList, modelViewer, imageViewer },
});
</script>
