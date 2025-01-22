<template>
<form @submit.prevent>
    <input
        v-model="message.report"
        class="input"
        type="text" 
        placeholder="Введите сообщение">
    <my-button-message
        class="btn"
        @click="addMessage">
        Отправить
    </my-button-message>
</form>
</template>

<script>
export default {
    data() {
        return {
            message:{
                report: ""
            }
        }
    },
    methods: {
        addMessage() {
            this.message.id = Date.now()
            this.$emit('add', this.message)
            this.message = {
                report: ""
            }
        }
    }
}
</script>

<style scoped>
.input{
    width: 40%;
    padding: 10px;
    border: 2px solid lightblue;
    margin-top: 10px;
    margin-right:10px;
}
</style>