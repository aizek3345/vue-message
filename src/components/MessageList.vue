<template>
    <div>
        <h3>Сообщения</h3>
        <messagw-item 
            v-for="message in messages"
            :message="message"
            :key="message.id"
            @removeMessage="$emit('removeMessage', message)"/>
    </div>
</template>

<script>
import MessagwItem from './MessagwItem'
export default {
    components: { MessagwItem },
    props: {
        messages: {
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>

</style>