<template>
    <input :value="modelValue" @input="updateInput" type="text">
</template>

<script>
    export default {
        name: 'my-input',
        props: {
            modelValue: [String, Number]
        },
        methods: {
            updateInput(event) {
                this.$emit('update:modelValue', event.target.value)
            }
        }
    }
</script>

<style scoped>
.input {
    width: 100%;
    padding: 11px 8px 8px 16px;
    margin-bottom: 16px;
    border: 1px solid #F0F1F7;
    border-radius: 8px;
    font-weight: normal;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.3px;
    
    }
.input::placeholder {
    color: #4B506D;
    opacity: 0.4;
    }
</style>