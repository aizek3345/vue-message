<template>
    <div class="app">
        <message-list :messages="messages" @removeMessage="removesMessage"/>
        <message-form @add="addMessage"/>
        <div class="total-messages">Всего сообщений в чате: {{ totalMessages }}</div>
    </div>
</template>

<script>
import MessageForm from './components/MessageForm'
import MessageList from './components/MessageList'

export default {
    components: {
        MessageForm,
        MessageList

    },
    data() {
        return {
            messages: [
                {
                    id: 1,
                    report: "Привет!",
                },
                {
                    id: 2,
                    report: "Как дела?",
                },
            ],
        }
    },
    methods: {
        addMessage(message) {
            message.isNew = true
            this.messages.push(message)
        },
        removesMessage(message) {
            this.messages = this.messages.filter(m => m.id !== message.id)
        }
    },
    computed: {
        totalMessages() {
            return this.messages.length
        }
    },
    watch: {
        messages: {
            handler(newMessages) {
                const lastMessage = newMessages[newMessages.length - 1]
                if (lastMessage.isNew) {
                    setTimeout(() => {
                        lastMessage.isNew = false
                    }, 5000)
                }
            },
            deep: true
        }
    }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app{
    padding: 20px;
}
.total-messages{
    margin-top: 10px;
}
</style>