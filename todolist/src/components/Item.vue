<template>
    <div class="itemBox">
        <li>
            <input type="checkbox" :checked="item.status" @change="handleStatusChanged(item.id)" />
            <div class="content">{{ item.content }}</div>
        </li>
    </div>
</template>

<script>
export default {
    name: 'Item',
    props: ['item', 'handleStatusChanged'],
}
</script>

<style scoped>
li {
    display: flex;
    align-items: center;
    margin: 10px;
    height: 50px;
    list-style: none;
    background-color: palevioletred;
}
input {
    margin: 0 5%;
    height: 25px;
    width: 25px;
}
</style>