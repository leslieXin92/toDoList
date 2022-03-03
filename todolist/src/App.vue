<template>
    <div class="box">
        <Add :addItem="addItem" />
        <List :list="list" :handleStatusChanged="handleStatusChanged" :deleteItem="deleteItem" />
        <Options
            :totalCount="totalCount"
            :completeCount="completeCount"
            :handleCheckAll="handleCheckAll"
        />
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
    computed: {
        totalCount () {
            return this.list.length
        },
        completeCount () {
            let len = 0
            this.list.map(item => {
                if (item.status) {
                    len++
                }
            })
            return len
        },
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
        },
        deleteItem (id) {
            this.list = this.list.filter(item => item.id != id)
        },
        handleCheckAll () {
            if (this.completeCount < this.totalCount) {
                this.list.map(item => item.status = true)
            } else {
                this.list.map(item => item.status = false)
            }
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
