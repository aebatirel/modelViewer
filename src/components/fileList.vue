<template>
  <div>
    <button class="q-ma-sm" @click="getFolderPaths">Get Folder Paths</button>
    <q-list class="q-ma-sm" padding bordered separator>
      <q-item
        v-for="folderPath in folderPaths"
        :key="folderPath"
        clickable
        v-ripple
      >
        <q-item-section> {{ folderPath }} </q-item-section>
      </q-item>
    </q-list>
  </div>
</template>

<script>
import fs from 'fs';
export default {
  data() {
    return {
      folderPaths: [],
    };
  },
  methods: {
    async getFolderPaths() {
      // Read the contents of the current directory
      const files = await fs.promises.readdir(process.cwd());

      // Filter the list of files to include only directories
      const folders = files.filter((file) => fs.statSync(file).isDirectory());

      // Map the list of directories to an array of their full paths
      this.folderPaths = folders.map((folder) => fs.realpathSync(folder));
    },
  },
};
</script>
