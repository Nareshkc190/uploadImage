<template>
<div class="dropper">
  <input type="file" v-if="isLoggedIn" @change="uploadImages($event.target.files)" multiple accept="image/*" />
  <span> Drag files here ! </span>
</div>
</template>

<script>
import {
  mapActions,
  mapGetters
} from 'vuex';
export default {
  name: 'UploadForm',
  computed: mapGetters(['isLoggedIn']),
  methods: mapActions(['uploadImages'])
};
</script>

<style scoped>
.dropper {
  height: 30vh;
  border: 2px dashed black;
  border-radius: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.dropper:hover {
  background-color: #eee;
}

input {
  width: 100%;
  height: 30vh;
  position: absolute;
  opacity: 0;

}
</style>
