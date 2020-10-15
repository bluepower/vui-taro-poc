<template>
  <image
    src="https://nikoni.top/images/others/cg.jpg"
    class="bg"
  />
  <v-cool-button
    :scale="0.8"
    class="btn-lt"
  />
  <v-cool-button
    :scale="0.8"
    class="btn-rt"
  />
  <v-one-piece/>
</template>

<script>
import VCoolButton from '../../../components/misc/cool-button/index.vue'
import VOnePiece from '../../../components/misc/op/index.vue'


export default {
  name: 'button-demo',

  components: {
    [VCoolButton.name]: VCoolButton,
    [VOnePiece.name]: VOnePiece
  }
}
</script>

<style>
.bg {
  width: 100vw;
}

.btn-lt {
  position: absolute;
  top: 200px;
  left: 200px;
}

.btn-rt {
  position: absolute;
  top: 200px;
  left: 350px;
}
</style>
