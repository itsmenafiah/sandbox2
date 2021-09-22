<template>
  <div>
    <h1>Sandbox</h1>
    <div class="row">
      <div class="col-sm-4">
        <input
          type="text"
          class="border border-info rounded-pill"
          v-model="vale"
          id="inputTitle"
        />
        <button
          @click="addTitle"
          type="button"
          class="btn btn-outline-info rounded-pill"
        >
          add
        </button>
        <div v-for="(item, i) in bookTitle" :key="i">
          <items-title :title="item" @del="deletedata" />
        </div>
      </div>
      <div class="col-sm-4">
        <input type="text" class="border border-info rounded-pill" />
        <button
          @click="addName"
          type="button"
          class="btn btn-outline-info rounded-pill"
        >
          add
        </button>
        <items-name />
      </div>
      <div class="col-sm-4">
        <div class="input-group mb-3">
          <select class="custom-select" id="inputGroupSelect02">
            <option selected>Choose...</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
          </select>
          <select class="custom-select" id="inputGroupSelect02">
            <option selected>Choose...</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
          </select>
        </div>

        <button
          @click="addCollab"
          type="button"
          class="btn btn-outline-info rounded-pill"
        >
          add
        </button>
        <items-collab />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      val: "",
      bookTitle: ["Harry Potter", "Dictionary"],
    };
  },
  computed: {
    vale: {
      set(value) {
        const [first, ...second] = value.split(" ");
        this.val = first.concat(second);
      },
    },
  },
  methods: {
    taddTitle() {
      const data = this.val;
      this.bookTitle.push(data);
    },
    deletedata(data) {
      this.bookTitle.remove(data);
    },
  },
};
</script>