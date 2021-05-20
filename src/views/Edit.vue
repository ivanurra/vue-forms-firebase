<template>
  Edit: {{$route.params.id}} - {{task}}
  <form @submit.prevent="updateTask(task)">
    <Input :task="task" />
  </form>
</template>

<script>
import {mapState, mapActions} from 'vuex';
import Input from '../components/Input.vue';

export default {
    components: { 
        Input,
    },
    computed: {
        ...mapState(['task'])
    },
    methods: {
        ...mapActions(['setTask', 'updateTask'])
    },
    created() {
        this.setTask(this.$route.params.id)
    }
}
</script>
