<template>
  <div class="row">
    <app-revised
      :rprog="{ val1:val1, val2:val2, val3:val3 }"
      @afterProgChanged="getProgAfterChanged"
    ></app-revised>
    <app-incorporate
      :col1="{value: col1, result: res1}"
      :col2="{value: col2, result: res2}"
      :col3="{value: col3, result: res3}"
      @afterChanged="getAfterChanged"
    ></app-incorporate>
    <app-existing></app-existing>
    <app-photo></app-photo>
  </div>
</template>
<script>
import Existing from "./components/ExistingProgramming";
import Revised from "./components/RevisedProgramming";
import Incorporate from "./components/IncorporateTheChange";
import Photo from "./components/Photo";
export default {
  data() {
    return {
      col1: 900,
      col2: 17,
      col3: 70,
      val1: 900,
      val3: 70,
      val2: 8.5,
      res1: true,
      res2: true,
      res3: true,
    };
  },
  computed: {},
  components: {
    appExisting: Existing,
    appRevised: Revised,
    appPhoto: Photo,
    appIncorporate: Incorporate,
  },
  methods: {
    getAfterChanged(event) {
      this[event.id] = event.value;
    },
    getProgAfterChanged(event) {
      this[event.id] = event.value;
    },
  },
  watch: {
    val1() {
      if (this.val1 == this.col1) this.res1 = true;
      else this.res1 = false;
    },
    col1() {
      if (this.val1 == this.col1) this.res1 = true;
      else this.res1 = false;
    },
    val2() {
      if (this.val2 == this.col2 / 2) this.res2 = true;
      else this.res2 = false;
    },
    col2() {
      if (this.val2 == this.col2 / 2) this.res2 = true;
      else this.res2 = false;
    },
    val3() {
      if (this.val3 == this.col3) this.res3 = true;
      else this.res3 = false;
    },
    col3() {
      if (this.val3 == this.col3) this.res3 = true;
      else this.res3 = false;
    },
  },
};
</script>
