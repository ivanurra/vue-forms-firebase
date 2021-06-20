<template>
  <input 
      type="text"
      class="form-control my-2"
      placeholder="Ingrese nueva tarea"
      v-model.trim="tarea.nombre"
    >
    <button 
      class="btn btn-dark mt-2 btn-block" 
      type="submit"
      :disabled="bloquear"
    >
      GUARDAR
    </button>
</template>

<script>
export default {
    props: {
        tarea: Object
    },
    computed: {
        bloquear(){
            return this.tarea.nombre.trim() === "" ? true : false
        }
  }
}
</script>