<template>

    <div class="container mt-5">

        <h1>Ajouter une tâche</h1>

        <form>
            <div class="form-group">
                <label for="action">Action</label>
                <input v-model="formData.tache" type="texte" id="action" class="form-control">
            </div>
            <button v-on:click.prevent="creationItem" class="btn btn-primary mt-3">Créer une tâche</button>
        </form>

        <ul>
            <li v-bind:key="index" v-for="(tache, index) in tableauTaches">
                <item :id="index" :tache="tache" :suppression="suppression"></item>
            </li>
        </ul>
    </div>
</template>

<script>
    import Item from './Item.vue'

    export default {
        name: 'Contenu',
        data(){
            return {
                formData: {
                    tache: ''
                },
                tableauTaches: ['JavaScript', 'Vue', 'Python', 'React']
            }
        },
        components: {
            'item': Item
        },
        methods: {
            creationItem: function(){
                this.tableauTaches.push(this.formData.tache)
                this.formData.tache = ''
            },
            suppression: function(e){
                console.log(e);
                console.log(e.target.parentNode.id);
                this.tableauTaches.splice(e.target.parentNode.id, 1)
            }
        }
    }
</script>

<style scoped>

h1{
    margin-top: 100px !important;
}
ul{
    list-style-type: none;
    padding: 0;
}

</style>