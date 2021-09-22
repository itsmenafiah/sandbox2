<template>
  <div>
    <div class="row my-3">
      <div class="col-sm-8">
        <p>{{ title }}</p>
      </div>
      <div class="col-sm-4">
        <button
          class="btn btn-outline-info"
          style="text-size: 20px"
          @click="gone"
        >
          Delete
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    title: { type: String, default: "" },
  },
  methods: {
    hapgoneus() {
      const data = this.title;
      this.$emit("del", data);
    },
  },
};
</script>