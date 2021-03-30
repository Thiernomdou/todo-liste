<template>
    <div class="container">

        <h1> Entrez des choses à faire</h1>
        <form>

            <div class="form-group">
                <label for="action">Action</label>
                <input v-model="formData.tache" type="text" id="action" class="form-control">
            </div>

            <button v-on:click.prevent="creationItem" class="btn btn-primary mb-2">Créer une tâche</button>

            <ul v-for="(tache, index) in tableauTaches" :key="index">
                <li>
                    <item :tache="tache" :suppression="suppression" :id="index"></item>
                </li>
            </ul>

        </form>



    </div>
</template>

<script>

import Item from './Item'
export default {
    name: 'Contenu',
    data() {
        return {
            formData: {
                tache: ''
            },
            tableauTaches: ['JavaScript', 'VueJS', 'React', 'Angular', 'Python']
        }
    },
    methods: {
        creationItem: function() {
            this.tableauTaches.push(this.formData.tache);
            this.formData.tache = '';
        },
        suppression: function(e) {
            this.tableauTaches.splice(e.target.parentNode.id, 1);
        }
    },
    components: {
        'item': Item
    }
}

</script>

<style scoped>

    h1 {
        padding-top: 100px!important;
        text-align:center;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

</style>