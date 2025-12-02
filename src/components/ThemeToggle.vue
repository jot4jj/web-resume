<script setup>
import Button from './ui/button/Button.vue';

defineProps({
    isDarkMode: {
        type: Boolean,
        required: true
    }
})

const emit = defineEmits(['toggle'])

const handleClick = () => {
    emit('toggle')
}
</script>

<template>
    <Button
        variant="ghost"
        @click="handleClick"
    >
    <slot></slot>
    </Button>
</template>