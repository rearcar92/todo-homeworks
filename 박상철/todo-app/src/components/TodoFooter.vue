<template>
    <div class="allClearBtn">
        <button v-on:click="clearBtn">clear All</button>
    </div>
</template>

<script>
export default {
    methods: {
        clearBtn: function() {
            this.$emit('clearAll');
        }
    }
}
</script>

<style scoped>
    button {
        font-size: 15px;
        color: red;
        background: none;
        border: none;
        box-shadow: 0 0 15px rgba(0,0,0,.05);
        padding: 10px 20px;
        margin: 20px 0 0 0;
    }
</style>
