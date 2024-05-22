<template>
    <div class="root">
        <h1>{{ text }}</h1>
        <div class="container">
            <div class="flex">
                <div class="img-wrapper">
                    <!--img v-show="isCatVisible" src="../assets/images/cat.jpg"-->
                    <img 
                        v-if="isCatVisible" 
                        :class="imgFilters"
                        :style="imgStyles"
                        src="../assets/images/cat.jpg"
                    >
                    <p v-else>кот скоро вернется</p>
                </div>
                <div class="controls">
                    <h2>Шаверма-кот</h2>
                    <h3>Фильтры</h3>
                    <div class="btn-group flex">
                        <button 
                            type="button"
                            :class="imgFilters.sepia ? 'active' : ''"
                            @click="imgFilters.sepia = !imgFilters.sepia"
                        >
                            Сепия
                        </button>
                        <button 
                            type="button"
                            :class="imgFilters.border ? 'active' : ''"
                            @click="imgFilters.border = !imgFilters.border"
                        >
                            Рамка
                        </button>
                        <button 
                            type="button"
                            :class="imgFilters.shadow ? 'active' : ''"
                            @click="imgFilters.shadow = !imgFilters.shadow"
                        >
                            Тень
                        </button>
                        <button 
                            type="button"
                            :class="imgFilters.small ? 'active' : ''"
                            @click="imgFilters.small = !imgFilters.small"
                        >
                            Уменьшить
                        </button>
                    </div>
                    <h3>Размер фото</h3>
                    <div class="btn-group flex">
                        <label>
                            Ширина: {{ imgSizes.currentWidth }}
                            <input
                                type="range"
                                :value="imgSizes.currentWidth"
                                @input="imgSizes.currentWidth = $event.target.value"
                                :min="imgSizes.minWidth"
                                :max="imgSizes.maxWidth"
                            >
                        </label>
                        <label>
                            Высота: {{ imgSizes.currentHeight }}
                            <input
                                type="range"
                                :value="imgSizes.currentHeight"
                                @input="imgSizes.currentHeight = $event.target.value"
                                :min="imgSizes.minHeight"
                                :max="imgSizes.maxHeight"
                            >
                        </label>
                    </div>
                    <div class="btn-group flex">
                        <label>
                            Поворот: {{ imgSizes.currentRotate }}
                            <input
                                type="range"
                                :value="imgSizes.currentRotate"
                                @input="imgSizes.currentRotate = $event.target.value"
                                :min="imgSizes.minRotate"
                                :max="imgSizes.maxRotate"
                            >
                        </label>
                    </div>
                    <button 
                        @click="isCatVisible = !isCatVisible"
                    >
                        {{ isCatVisible ? btnText.hidden : btnText.show }}
                        <!-- или -->
                        <!-- {{ isCatVisible ? 'Показать' : 'Спрятать' }} -->
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
            text: 'Hello from 22.05.2024',
            isCatVisible: true, 
            imgFilters: {
                sepia: false,
                border: false,
                small: false
            },
            imgSizes: {
                maxWidth: 640,
                maxHeight: 480,
                currentWidth: 640,
                currentHeight: 480,
                maxRotate: 360,
                currentRotate: 0
            },
            btnText: {
                show: "Показать",
                hidden: "Спрятать"
            }
        }
    },
    computed: {
        imgStyles() {
            return {
                width: `${this.imgSizes.currentWidth}px`,
                height: `${this.imgSizes.currentHeight}px`,
                transform: `rotate(${this.imgSizes.currentRotate}deg)`
            }
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
.shadow {
    box-shadow: 3px 3px red, -1em 0 .4em olive;
}
.small {
    width: 400px;
}
button {
    margin-right: 10px;
}
button:active,
button.active {
    background-color: #00bfff;
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