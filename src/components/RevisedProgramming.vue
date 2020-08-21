<template>
  <div class="col-sm-6">
    <div class="bg-white box box-editor">
      <h3 class="text-center text-danger">Revised Programming</h3>
      <div>
        <pre>
        N1 T0101
        N2 G97 S<input id="val1" @input="onchange" type="text" :value="rprog.val1" />M03
        N3 G42 G00 X0 Z0
        N4 G01 X25 G95 F0.3
        N5 G01 Z-<input
  id="val2"
  @input="onchange"
  type="text"
  :value="rprog.val2"
/>
        N6 G01 X40 Z-15
        N7 G01 Z-25
        N8 G01 X<input
  class="r-input"
  id="val3"
  @input="onchange"
  type="text"
  :value="rprog.val3"
/> Z-35
        N9 G40 G00 X200 Z100
      </pre>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["rprog"],
  methods: {
    onchange(e) {
      this.$emit("afterProgChanged", {
        id: e.target.id,
        value: e.target.value,
      });
    },
  },
};
</script>