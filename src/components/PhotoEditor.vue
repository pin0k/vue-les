<template>
    <div class="root">
        <h1>{{ text }}</h1>
        <div class="container">
            <div class="flex">
                <div class="img-wrapper">
                    <img src="../assets/images/cat.jpg">
                </div>
                <div class="controls">
                    <h2>Шаверма-кот</h2>
                    <button @click="isCatVisible = !isCatVisible">
                        Показать / спрятать
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PhotoEditor',
    data() {
        return {
            text: 'Hello from 17.05.2024',
            isCatVisible: true, 
        }
    }
}
</script>
<style>
.container {
    margin-top: 40px;
}
.flex {
    display: flex;
}
.controls {
    margin-left: 20px;
}
.img-wrapper {
    width: 640px;
    height: 480px;
    background-color: #cecece;
}
img {
    transition: 0.2s ease;
}
.sepia {
    filter: sepia(100%);
}
.border {
    border: 5px dashed #464646
}
.small {
    width: 400px;
}
button {
    margin-right: 10px;
}
button:active {
    background-color: #dbdbdb;
}
h2 {
    margin-bottom: 10px;
}
.btn-group {
    margin-bottom: 20px;
}
input[type="range"] {
    display: block;
}
</style>