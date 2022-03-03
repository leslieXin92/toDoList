<template>
    <div class="box">
        <Add :addItem="addItem" />
        <List :list="list" />
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
                { id: '001', content: '1', status: 1 },
                { id: '002', content: '2', status: 0 },
                { id: '003', content: '3', status: 1 },
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
                status: 0
            }
            this.list.unshift(newItem)
            e.target.value = ''
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
