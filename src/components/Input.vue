<template>
  <input
    type="text"
    class="form-control my-2"
    placeholder="Write your name"
    v-model.trim="task.name"
  />
  <br />
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      id="check-1"
      class="form-check-input"
      v-model="task.categories"
      value="JavaScript"
    />
    <label for="check-2" class="form-check-label">JavaScript</label>
  </div>
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      id="check-1"
      class="form-check-input"
      v-model="task.categories"
      value="NodeJS"
    />
    <label for="check-3" class="form-check-label">NodeJS</label>
  </div>
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      id="check-1"
      class="form-check-input"
      v-model="task.categories"
      value="VueJS"
    />
    <label for="check-4" class="form-check-label">VueJS</label>
  </div>
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      id="check-1"
      class="form-check-input"
      v-model="task.categories"
      value="ReactJS"
    />
    <label for="check-1" class="form-check-label">ReactJS</label>
  </div>
  <div class="mt-2">
    <div class="form-check form-check-inline">
      <input
        type="radio"
        id="radio-1"
        class="form-check-input"
        value="prority"
        v-model="task.status"
      />
      <label for="radio-1" class="form-check-label">Priority</label>
    </div>
    <div class="form-check form-check-inline">
      <input
        type="radio"
        id="radio-2"
        class="form-check-input"
        value="nopriority"
        v-model.number="task.status"
      />
      <label for="radio-2" class="form-check-label">No Priority</label>
    </div>
  </div>
  <div class="mt-2">
    <input type="number" class="form-control" v-model="task.number" />
  </div>
  <button class="btn btn-dark mt-2 btn-block" type="submit" :disabled="blocked">
    Enter
  </button>
</template>

<script>
export default {
  props: {
    task: Object,
  },
  computed: {
    blocked() {
      return this.task.name.trim() === "" ? true : false;
    },
  },
}
</script>