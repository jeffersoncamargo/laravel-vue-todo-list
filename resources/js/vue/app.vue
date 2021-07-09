<template>
    <div class="list-container">
        <div class="heading">
            <h2 id="title">Laravel and Vue.js ToDo List</h2>
            <item-form v-on:itemcreated="getItems()" />
        </div>
        <list :items="items" v-on:reloadlist="getItems()" />
    </div>
</template>

<script>
import ItemForm from "./form"
import List from "./list"
export default {
    components: {
        ItemForm,
        List
    },
    data: function() {
        return {items: []}
    },
    methods: {
        getItems () {
            axios.get(
                'api/items'
            )
            .then(response => {
                this.items = response.data
            }).catch(error => {
                console.log(error)
            })
        }
    },
    created() {
        this.getItems()
    }
}
</script>

<style scoped>
    .list-container {
        width: 350px;
        margin: 0 auto;
    }
    .heading {
        background-color: #e6e6e6;
        padding: 10px;
    }
    #title {
        text-align: center;
    }
</style>