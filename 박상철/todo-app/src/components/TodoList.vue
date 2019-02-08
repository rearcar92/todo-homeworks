<template>
    <div>
        <ul>
            <li v-for="(todoItem, index) in propsTodoItems" v-bind:key="todoItem.item" class="shadow">
              <i class="checkBtn fas fa-check" v-bind:class="{checkBtnCompleted: todoItem.completed}" v-on:click="toggleComplete(todoItem, index)"></i>
              <span v-bind:class="{textCompleted: todoItem.completed}">{{ todoItem.item }}</span>
              <span class="removeBtn" v-on:click="todoRemove(todoItem, index)">
                <i class="fas fa-trash"></i>
              </span>
            </li>
            
        </ul>
    </div>
</template>

<script>
export default {
  props: ['propsTodoItems'],
  methods: {
    todoRemove: function(todoItem, index) {
      this.$emit('removeItem', todoItem, index);
    },
    toggleComplete: function(todoItem, index) {
      this.$emit('toggleItem', todoItem, index);
    }
  },
   
}
</script>

<style scoped>
  ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  ul li {
    display: flex;
    height: 45px;
    line-height: 45px;
    margin: 10px 0;
    padding: 0 10px;
    background: #fff;
  }
  .removeBtn {
    margin-left: auto;
    color: red;
    line-height: 45px;
    opacity: .4;
  }
  .checkBtn {
    line-height: 45px;
    color: #62acde;
    margin-right: 5px;
  }
  .checkBtnCompleted {
    color: #b3adad;
  }
  .textCompleted {
    text-decoration: line-through;
    color: #b3adad;
  }
</style>
