<script setup>
let times;
const func = () => {
    times = setInterval(() => {
        const d = new Date();
        const newh = d.getHours();
        const newm = d.getMinutes();
        const news = d.getSeconds();
        const hrotation = 30 * newh + newm / 2;
        const mrotation = 6 * newm;
        const srotation = 6 * news;
        hour.style.transform = `rotate(${hrotation}deg)`;
        minute.style.transform = `rotate(${mrotation}deg)`;
        second.style.transform = `rotate(${srotation}deg)`;
    }, 1000);
}
const copy = () => {
    clearInterval(times);
}

</script>

<template>
    <div id="container">
        <div id="hour"></div>
        <div id="minute"></div>
        <div id="second"></div>
    </div>
    <button @click="func">start</button>
    <button @click="copy">stop</button>
</template>

