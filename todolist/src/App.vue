<template>
    <div class="box">
        <Add :addItem="addItem" />
        <List :list="list" :handleStatusChanged="handleStatusChanged" />
        <Options />
    </div>
</template>

<script>
import Add from './components/Add'
import List from './components/List'
import Options from './components/Options'

export default {
    name: 'App',
    components: {
        Add,
        Options,
        List
    },
    data () {
        return {
            list: [
                { id: '001', content: 'Vue', status: true },
                { id: '002', content: 'node', status: false },
                { id: '003', content: 'websocket', status: false },
            ]
        }
    },
    methods: {
        addItem (e) {
            if (!e.target.value.trim()) {
                e.target.value = ''
                return
            }
            const newItem = {
                id: new Date().getTime(),
                content: e.target.value.trim(),
                status: false
            }
            this.list.unshift(newItem)
            e.target.value = ''
        },
        handleStatusChanged (id) {
            this.list.map(item => {
                if (item.id === id) {
                    item.status = !item.status
                }
            })
        }
    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.box {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 20px auto;
    width: 60%;
    /* outline: 1px solid red; */
    background-color: palegreen;
}
</style>
