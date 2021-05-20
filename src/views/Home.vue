<template>
  <form @submit.prevent="processForm">
   <Input :task="task" />
  </form>
  <br />
  <Tasks-list />
</template>

<script>
import Input from '../components/Input';
import {mapActions} from 'vuex';
import TasksList from '../components/TasksList.vue';
const shortid = require('shortid');

export default {
  name: "Home",
  components: {
    Input,
    TasksList,
  },
  data() {
    return {
      task: {
        id: '',
        name: '',
        categories: [],
        status: '',
        number: 0,
      },
    };
  },
  methods: {
    ...mapActions(['setTasks']),
    processForm() {
      console.log(this.task);
      if (this.task.name.trim() === "") {
        console.log("Empty");
        return;
      }
      console.log("Not empty");

      this.task.id = shortid.generate();
      console.log(this.task.id);

      this.setTasks(this.task)

      this.task = {
        id:'',
        name: "",
        categories: [],
        status: "",
        number: 0,
      };
    },
  },
  computed: {
    blocked() {
      return this.task.name.trim() === "" ? true : false;
    },
  },
};
</script>
