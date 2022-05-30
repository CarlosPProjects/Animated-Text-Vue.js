<template>
    <!--We must bind the attribute if we want to get 'text' value-->
    <h2 :data-text = "props.text" > {{ props.text }} </h2>
</template>

<script setup>

const props = defineProps({
    text: String
});

</script>

<style>
h2 {
    position: relative;
    font-size: 14vw;
    color: #252839;
    -webkit-text-stroke: 0.3vw #383d52;
    text-transform: uppercase;
}

h2::before {
    content: attr(data-text);
    position: absolute;
    top: 0;
    left: 0;
    width: 0;
    height: 100%;
    color: #01fe87;
    -webkit-text-stroke: 0vw #383d52;
    border-right: 2px solid #01fe87;
    overflow: hidden;
    animation: animate 6s linear infinite;
}

@keyframes animate {

    0%,
    10%,
    100% {
        width: 0;
    }

    70%,
    90% {
        width: 100%;
    }
}
</style>