<template>
  <div class="col-sm-6">
    <div class="box right-box">
      <table class="table my-auto">
        <tr>
          <th>Incorporate the Change</th>
          <th>Target</th>
          <th>Result</th>
        </tr>
        <tr>
          <td>Change the Speed to ---></td>
          <td>
            <input type="text" id="col1" :value="col1.value" @input="onChange" />
          </td>
          <td>
            <span v-if="col1.result">Pass</span>
            <span v-else>Try Again</span>
          </td>
        </tr>
        <tr>
          <td>Reduce the Dia of P1 to ---></td>
          <td>
            <input type="text" id="col2" :value="col2.value" @input="onChange" />
          </td>
          <td>
            <span v-if="col2.result">Pass</span>
            <span v-else>Try Again</span>
          </td>
        </tr>
        <tr>
          <td>Increase Dia of P4 to ---></td>
          <td>
            <input type="text" id="col3" :value="col3.value" @input="onChange" />
          </td>
          <td>
            <span v-if="col3.result">Pass</span>
            <span v-else>Try Again</span>
          </td>
        </tr>
      </table>
      <div class="alert" :class="{'alert-success': status,'alert-danger': !status}">
        <span v-if="status">Success!</span>
        <span v-else>Warning!</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["col1", "col2", "col3"],
  computed: {
    status: function () {
      if (this.col1.result && this.col2.result && this.col3.result) return true;
      return false;
    },
  },
  methods: {
    onChange(e) {
      this.$emit("afterChanged", { id: e.target.id, value: e.target.value });
    },
  },
};
</script>