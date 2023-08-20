<template>
    <div class="parent-component">
        <h2>Welcome to the Parent Component</h2>
        <ChildComponent :message="message" @messageEmitted="handleMessage" />
        <p class="received-message">Message from Child Component:  {{ receivedMessage }}</p>
    </div>
</template>

<script>
import { defineProps, ref } from 'vue';
import ChildComponent from './ChildComponent.vue';

export default {
    components: {
        ChildComponent,
    },
    setup() {
        const receivedMessage = ref('');

        const handleMessage = (message) => {
            receivedMessage.value = message;
        };

        return {            
            receivedMessage,
            handleMessage,
        };
    },
};
</script>

<style scoped>
.parent-component {
    background-color: #f2f2f2;
    padding: 20px;
}

.parent-component h2 {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 10px;
}

.parent-component p {
    margin-bottom: 10px;
}

.parent-component .received-message {
  background-color: #5cd7df;
  padding: 10px;
  border-radius: 4px;
}
</style>
