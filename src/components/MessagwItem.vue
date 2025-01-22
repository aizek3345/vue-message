<template>
<div :class="['message', { 'new-message': message.isNew }]">
    <div>Сообщение: {{ message.report }}</div>  
    <div>
        <my-button-message @click = "$emit('removeMessage', message)">Удалить</my-button-message>
    </div>
</div>

</template>
    
<script>
export default {
    props: {
        message: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>
.new-message {
    background-color: lightyellow;
}
.message{
    padding: 15px;
    border: 2px solid lightblue;
    margin-top: 10px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>