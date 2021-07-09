<template>
    <div class="item-form">
        <input type="text" v-model="item.name" />
        <font-awesome-icon
            icon="plus-square"
            @click="addItem()"
            :class="[item.name ? 'active' : 'inactive', 'plus']" />
    </div>
</template>

<script>
export default {
    data: () => ({
        item: {
            name: ""
        }
    }),
    methods: {
        addItem() {
            if(!this.item.name) {
                alert('Informe o nome do item')
                return
            }

            axios.post('api/item', {
                name: this.item.name
            })
            .then(response => {
                if(response.status == 201) {
                    this.item.name = ""
                    this.$emit('itemcreated')
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
    .item-form {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    input {
        background-color: #f7f7f7;
        border: 0;
        outline: none;
        padding: 5px;
        margin-right: 10px;
        width: 100%;
    }
    .active {
        color: #00ce25;
    }
    .inactive {
        color: #999;
    }
    .plus {
        font-size: 20px;
    }
</style>