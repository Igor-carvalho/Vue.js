<template>
    <div class='ui centered card'>
        <!--// Todo shown when we are not in editing mode.-->
        <div class="content" v-show="!isEditing">
            <div class='header'>
                {{ todo.title }}
            </div>
            <div class='meta'>
                {{ todo.project }}
            </div>
            <div class='extra content'>
                <span class='right floated edit icon' v-on:click="showForm">
                    <i class='edit icon'></i>
                </span>
                <!--/* add the trash icon in below the edit icon in the template */-->
                <span class='right floated trash icon' v-on:click="deleteTodo(todo)">
                  <i class='trash icon'></i>
                </span>
            </div>
        </div>
        <!--// form is visible when we are in editing mode-->
        <div class="content" v-show="isEditing">
            <div class='ui form'>
                <div class='field'>
                    <label>Title</label>
                    <input type='text' v-model="todo.title" >
                </div>
                <div class='field'>
                    <label>Project</label>
                    <input type='text' v-model="todo.project" >
                </div>
                <div class='ui two button attached buttons'>
                    <button class='ui basic blue button' v-on:click="hideForm">
                        Close X
                    </button>
                </div>
            </div>
        </div>
        <div class='ui bottom attached green basic button' v-show="!isEditing &&todo.done" disabled>
            Completed
        </div>
        <div v-on:click="completeTodo(todo)"
             class='ui bottom attached red basic button' v-show="!isEditing && !todo.done">
            Pending
        </div>
    </div>
</template>

<script>
export default {
  props: ['todo'],
  name: 'Todo',
  data() {
    return {
      isEditing: false,
    };
  },
  methods: {
    showForm() {
      this.isEditing = true;
    },
    hideForm() {
      this.isEditing = false;
    },
    deleteTodo(todo) {
      this.$emit('delete-todo', todo);
    },
    completeTodo(todo) {
      this.$emit('complete-todo', todo);
    },
  },
};
</script>

<style scoped>

</style>
