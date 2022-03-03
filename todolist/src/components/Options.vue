<template>
    <div class="optionsBox">
        <input type="checkbox" />
        <div>已完成 0 / 全部 6</div>
        <button>清除已完成</button>
    </div>
</template>

<script>
export default {
    name: 'Options'

}
</script>

<style scoped>
.optionsBox {
    display: flex;
    align-items: center;
    width: 80%;
    height: 50px;
    background-color: aquamarine;
}
input {
    width: 25px;
    height: 25px;
    margin: 0 5%;
}
button {
    width: 15%;
    height: 35px;
    margin-left: 40%;
}
</style>