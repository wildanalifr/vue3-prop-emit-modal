<template>
  <div>{{pesan}}</div>
</template>

<script>
export default {
  props: ["halo"],
  watch: {
    halo: function (newVal) {
      this.pesan = newVal;
    },
  },
  setup(props) {
    let pesan = props.halo;
    return {
      pesan,
    };
  },
};
</script>