<template>
    <div class="card-wrapper">
        <div class="card">
            <div class="card-left">
            <h2>Your Result</h2>
            <h1>76</h1>
            <h3>of 100</h3>
            <h2>Great</h2>
            <p>
                You scored higher than 65% of the people who have taken these tests.
            </p>
            </div>
            <div class="card-right">
                <h2>Summary</h2>
                <div v-for=" (data, index ) in dataList" :key="data.category" class="dataBar" :style="colors[index]">
                    <!-- img with path of data.icon -->
                    <div class="icon" :style="colors[index]">
                        <img :src=data.icon alt="icon">
                    </div>
                    <h3 :style="TextColors[index]">{{data.category}}</h3>
                    <div class="score-end">
                        <span class="strong">{{data.score}}</span>
                        <span class="weak">/ 100</span>
                    </div>

                </div>
                <button>Continue</button>
            </div>
        </div>

    </div>
</template>

<script setup>
import { ref } from 'vue'

const dataList = ref([
  {
    "category": "Reaction",
    "score": 80,
    "icon": "/src/assets/images/icon-reaction.svg",
  },
  {
    "category": "Memory",
    "score": 92,
    "icon": "/src/assets/images/icon-memory.svg"
  },
  {
    "category": "Verbal",
    "score": 61,
    "icon": "/src/assets/images/icon-verbal.svg"
  },
  {
    "category": "Visual",
    "score": 72,
    "icon": "/src/assets/images/icon-visual.svg"
  }
]);
        // --primary-light-red: hsl(0, 100%, 67%);
        // --primary-orangey-yellow: hsl(39, 100%, 56%);
        // --primary-green-teal: hsl(166, 100%, 37%);
        // --primary-cobalt-blue: hsl(234, 85%, 45%);
const colors = ref([
    `background-color:hsl(0, 100%, 67%, 0.05)`,
    `background-color:hsl(39, 100%, 56%, 0.05)`,
    `background-color:hsl(166, 100%, 37%, 0.05)`,
    `background-color:hsl(234, 85%, 45%, 0.05)`
]);

const TextColors = ref([
    `color:hsl(0, 100%, 67%)`,
    `color:hsl(39, 100%, 56%)`,
    `color:hsl(166, 100%, 37%)`,
    `color:hsl(234, 85%, 45%)`
]);

</script>

<style scoped>
    .card-wrapper{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .card{
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        max-width: 760px;
        height: 500px;
        background-color: var(--neutral-white);
        border-radius: 30px;
        box-shadow: 0px 0px 30px 0px rgba(50, 79, 238, 0.517);
    }

    .card-left{
        width: 50%;
        height: 100%;

        /* vertical gradient bacground  var(--gradient-light-slate-blue) var(--gradient-light-royal-blue) */
        background: linear-gradient(180deg, var(--gradient-light-slate-blue) 0%, var(--gradient-light-royal-blue) 100%);
        border-radius: 30px;
    }

    .card-right{
        width: 50%;
        height: 100%;
        border-radius: 0 20px 20px 0;

        /* flex */
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: start;

    }

    .card-left h2{
        color: var(--neutral-white);
        font-size: 24px;
        font-weight: 700;
        margin: 20px 0 0 20px;
    }

    .card-left h1{
        color: var(--neutral-white);
        font-size: 120px;
        font-weight: 700;
        margin: 20px 0 0 20px;
    }

    .card-left h3{
        color: var(--neutral-white);
        font-size: 24px;
        font-weight: 700;
        margin: 0 0 0 20px;
    }

    .card-left p{
        color: var(--neutral-white);
        font-size: 18px;
        font-weight: 400;
        margin: 20px 0 0 20px;
    }

    .card-right h2{
        color: var(--neutral-dark-blue);
        font-size: 24px;
        font-weight: 700;
        margin: 20px 0 0 40px;
    }

    .dataBar{
        width:300px;
        height: 60px;
        display: flex;
        align-items: center;
        margin: 0 0 0 40px;
        border-radius: 10px;
    }

    .dataBar h3{
        color: var(--neutral-dark-blue);
        font-size: 18px;
        font-weight: 700;
        margin: 0 0 0 20px;
    }

    .dataBar span{
        /* color: var(--neutral-dark-blue); */
        font-size: 18px;
        font-weight: 400;
        margin: 0 0 0 20px;
    }   

    .dataBar .icon{
        width: 40px;
        height: 40px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .dataBar .icon img{
        width: 20px;
        height: 20px;
    }

    .card-right button{
        width: 290px;
        height: 55px;

        background-color: var(--neutral-dark-gray-blue);
        border-radius: 50px;
        border: none;
        color: var(--neutral-white);
        font-size: 18px;
        font-weight: 700;
        margin-bottom: 40px;
        margin-left: 40px;
    }

    .card-right button:hover{
        background-color: var(--gradient-light-royal-blue);
    }

    .score-end{
        display: flex;
        align-items: center;
        margin: 0 0 0 40px;
    }

    .score-end .strong{
        font-weight: 700;

    }

    .score-end .weak{
        font-weight: 400;
    }


</style>