<template>
    <div class="itemBox">
        <ul>
            <li v-for="item in list" :key="item.id">
                <input type="checkbox" />
                <div class="content">{{ item.content }}</div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Item',
    data () {
        return {
            list: [
                { id: '001', content: '1', status: 1 },
                { id: '002', content: '2', status: 0 },
                { id: '003', content: '3', status: 1 },
            ]
        }
    },

}
</script>

<style scoped>
ul {
    margin: 0 auto;
}
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