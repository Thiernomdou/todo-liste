<template>
    <div class="card my-2 item-todo">

        <p>{{ tache }}</p>
        <div v-on:click="suppression" class="btn btn-danger btn-supr">X</div>

    </div>
</template>

<script>
export default {
    name: 'Item',
    props: ['tache', 'suppression']
}
</script>

<style scoped>

.item-todo {
    position: relative;
    top: 10px;
    font-size: 20px;
    height: 88px;
}
.btn-supr {
    position: absolute;
    top: 10px;
    right: 10px;
}

</style>