<template>
    <button 
        class="btn"
        >
        <slot>
            
        </slot>
    </button>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
.btn {
    margin-top: 14px;
    border: none;
    border-radius: 8px;
    width: 100%;
    height: 48px;
    background-color: #212121;
    color: #fff;
}
</style>