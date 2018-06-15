<template>
  <div class='day-header'>
    <h1>{{ dayTitle }}</h1>
    <button v-on:click="addPlan">+</button>
    <modal v-bind:name="modalName">
      <h2>Add Plan!</h2>   
    </modal> 
  </div>
</template>

<script>
  export default {
      props: ['dayTitle'],
      data() {
        return {
          plans: [],
        }
      },
      methods: {
        addPlan() {
          //this.showModal = true;
          console.log('add');
          this.$modal.show(this.modalName);
        }
      },
      computed: {
          modalName(){ 
            return 'plan-modal-' + this.dayTitle;
          }
      }
  }
</script>

<style scoped>
.day-header {
  display: flex;
  align-items: center;
}
</style>