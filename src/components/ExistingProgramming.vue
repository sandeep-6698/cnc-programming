<template>
  <div class="col-sm-6">
    {{text}}
    <div class="bg-white box box-editor">
      <h3 class="text-center text-success">Existing Programming</h3>
      <div>
        <pre>
        N1 T0101
        N2 G97 S500 M03
        N3 G42 G00 X0 Z0
        N4 G01 X25 G95 F0.3
        N5 G01 Z-7.5
        N6 G01 X40 Z-15
        N7 G01 Z-25
        N8 G01 X60 Z-35
        N9 G40 G00 X200 Z100
      </pre>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      text: this.$refs.exist,
    };
  },
  methods: {
    prog1(e) {
      this.text = e.target.innerText.indexOf("S500");
    },
  },
};
</script>