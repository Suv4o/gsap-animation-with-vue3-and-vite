<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";

const logo = ref(null);
let tl = null;

onMounted(() => {
    tl = gsap.timeline();
    tl.from(logo.value, {
        x: -300,
        backgroundColor: "#f0c690",
        borderRadius: "20%",
        border: "5px solid grey",
        duration: 2,
        ease: "bounce",
    });
    tl.from(
        ".circle",
        {
            y: "random(-200, 200)",
            opacity: 0,
            duration: 1,
            stagger: 0.15,
        },
        "+=1"
    );
});
</script>

<template>
    <img ref="logo" src="./assets/logo.png" alt="Logo" />
    <div class="circle circle--blue"></div>
    <div class="circle circle--red"></div>
    <div class="circle circle--yellow"></div>
    <div class="circle circle--green"></div>
    <div class="circle circle--purple"></div>
    <div class="circle circle--pink"></div>
</template>

<style>
html,
body {
    font-size: 100%;
    overflow-x: hidden;
    align-content: center;
    background-color: #efe8df;
    color: #173353;
    display: grid;
    justify-content: center;
    width: 100vw;
    height: 100vh;
}

*,
*::before,
*::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    line-height: 1.3;
}

a {
    text-decoration: none;
}

.circle {
    margin-left: 10px;
    margin-right: 10px;
    display: inline-block;
    width: 100px;
    height: 100px;
    border-radius: 50%;
}

.circle--blue {
    background-color: blue;
}

.circle--red {
    background-color: red;
}

.circle--yellow {
    background-color: yellow;
}

.circle--green {
    background-color: green;
}

.circle--purple {
    background-color: purple;
}

.circle--pink {
    background-color: pink;
}

.actions {
    display: flex;
    margin: 40px 0;
    justify-content: center;
}

.actions button {
    font-size: 48px;
    border: 0;
    margin-left: 10px;
    margin-right: 10px;
    padding: 5px;
    background-color: brown;
    color: white;
    cursor: pointer;
}

.actions button:hover {
    background-color: goldenrod;
}
</style>
