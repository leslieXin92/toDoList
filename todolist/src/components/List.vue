<template>
    <div class="listBox">
        <Item />
        <Item />
    </div>
</template>

<script>
import Item from './Item'

export default {
    name: 'List',
    components: {
        Item
    }
}
</script>

<style>
.listBox {
    width: 80%;
    height: auto;
    margin: 0px auto;
}
</style>