<template>
    <div>
        <span
            @click="completeItem(item)"
            class="name">
            {{ item.name }}
        </span>
        <font-awesome-icon
            icon="trash"
            class="trash"
            @click="removeItem(item)" />
    </div>
</template>

<script>
export default {
    props: ['item', 'i'],
    methods: {
        completeItem (item) {
            axios.put('api/item/' + item.id, {
                completed: 1
            })
            .then(response => {
                if (response.status == 200) {
                    this.$emit('itemchanged')
                }
            })
            .catch(error => {
                console.log(error)
            })
        },
        removeItem (item) {
            axios.delete(
                'api/item/' + item.id
            )
            .then(response => {
                if (response.status == 200) {
                    this.$emit('itemchanged')
                }
            })
            .catch(error => {
                console.log(error)
            })
        }
    }
}
</script>

<style scoped>
    .incomplete .name {
        cursor: pointer;
    }
    .complete .name {
        color: #757575;
        text-decoration: line-through;
        cursor: initial;
    }
    .trash {
        color: red;
        cursor: pointer;
    }
</style>