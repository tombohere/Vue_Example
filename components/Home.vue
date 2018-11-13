<template>
  <div id="home" class="nav_content">
    <div>
      <div class="box1">
        This is my Vue example program. It incorporates<br />
        <ul>
          <li>Vue.js</li>
          <li>vue-router</li>
          <li>vee-validate</li>
          <li>vue-localstorage</li>
          <li>vuefire + firebase</li>
          <li>jsonbin.io (web api for storing json data)</li>
        </ul>
        <button
          v-bind:style="{
            'background-image':
              'url(' + $parent.chars[$parent.select[0].select].img + ')'
          }"
          @click="chooseCharacter"
        ></button
        ><br />
        Click above to change character
      </div>
    </div>
    <transition name="appear">
      <modalCharacter v-if="confirmModal"></modalCharacter>
    </transition>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      confirmModal: false
    };
  },
  methods: {
    chooseCharacter() {
      this.confirmModal = true;
    }
  }
};
</script>

<style scoped>
#home {
  /*  background-image: url(https://unsplash.it/500/800/?random&1);*/
  background-color: #799db8;
  background-image: url("https://www.transparenttextures.com/patterns/subtle-grey.png");
  /* This is mostly intended for prototyping; please download the pattern and re-host for production environments. Thank you! */
}

.box1 {
  border-radius: 12px;
  background-color: rgba(255, 255, 255, 0.5);
  padding: 10px;
  font-size: 20px;
  font-weight: bold;
  background-image: url(https://vuejs.org/images/logo.png);
  background-size: 100px;
  background-repeat: no-repeat;
  background-position: right bottom;
}

button {
  font-size: 32px;
  border-radius: 99px;
  height: 100px;
  width: 100px;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center center;
  outline: none;
  background-color: lightsteelblue;
}
</style>
