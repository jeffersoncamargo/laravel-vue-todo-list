<template>
    <div>
        <div v-for="(item, i) in items" :key="i">
            <item
                :item="item"
                :class="[item.completed ? 'complete' : 'incomplete', 'item']"
                v-on:itemchanged="$emit('reloadlist')" />
        </div>
    </div>
</template>

<script>
import Item from "./item"
export default {
    props: ['items'],
    components: {
        Item
    }
}
</script>

<style scoped>
    .item {
        background: #e6e6e6;
        padding: 5px;
        margin-top: 5px;
        display: flex;
        justify-content: space-between;
    }
</style>