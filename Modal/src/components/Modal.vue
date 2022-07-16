<template>
    <div class="overlay" @click.self="closeModal">
        <div class="modal" :class="{sale: theme==='sale'}">
            <h1>{{header}}</h1>
            <p>{{text}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['header', 'text', 'theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
    .overlay {
        width: 100%;
        height: 100%;
        position: fixed;
        top: 0;
        left: 0;
        background-color: rgba(0, 0, 0, 0.6);
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
    }
    .overlay .modal {
        width: 500px;
        height: 200px;
        background-color: #fff;
        justify-content: center;
        align-items: center;
        cursor: default;
        border-radius: 10px;
    }
    
    .overlay .modal h1 {
        padding-top: 30px;
        font-weight: 800;
        font-size: 36px;
        color: rgb(2, 235, 118);
    }

    .overlay .sale {
        background-color: rgb(230, 36, 68);
        color: #fff !important;
    }
    
    .overlay .modal p {
        font-weight: 600;
        font-size: 18px;
        padding-top: 20px;
    }
</style>