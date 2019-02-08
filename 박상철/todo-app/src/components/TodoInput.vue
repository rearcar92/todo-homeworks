<template>
    <div class="input_box">
        <input type="text" placeholder="내용을 입력하세요." v-model="newItem"  v-on:keyup.enter="addTodo">
        <span class="addBtn">
            <i v-on:click="addTodo" class="fas fa-plus"></i>
        </span>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            newItem: '',
        }
    },
    
    methods: {
        addTodo: function() {
            if (this.newItem !== "") {
                this.$emit('addTodoItem', this.newItem);
                this.clearInput();
            } 
        },
        clearInput: function() {
            this.newItem = '';
        }
    }
    
}
</script>

<style scoped>
    input:focus {
        outline: none;
    }
    .input_box {
        background: #fff;
        box-shadow: 5px 10px 10px rgba(0,0,0,.05);
        line-height: 50px;
        height: 50px;
        border: 1px solid #eee;
    }
    .input_box input {
        border: none;
        text-align: center;
    }
    .addBtn {
        width: 3rem;
        float: right;
        background: #96ccc3;
        color: #fff;
        border-radius: 0 5px 5px 0;
    }
</style>
