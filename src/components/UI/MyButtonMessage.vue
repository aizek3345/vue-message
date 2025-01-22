<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>
        
<script>
export default {
    name: "my-button-message"
}
</script>
        
<style scoped>
.btn{
    padding: 10px;
    background: none;
    border: 2px solid lightblue;
}
</style>