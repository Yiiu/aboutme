<template>
    <svg class="next" height="24" viewBox="0 0 24 24" width="24" xmlns="http://www.w3.org/2000/svg">
        <path d="M7.41 7.84L12 12.42l4.59-4.58L18 9.25l-6 6-6-6z"></path>
        <path d="M0-.75h24v24H0z" fill="none"></path>
    </svg>
</template>
<style lang="less">
    .next {
        position: absolute;
        bottom: 42px;
        animation-name: next;
        animation-duration: 2s;
        animation-timing-function: cubic-bezier(.86,0,.07,1);
        animation-iteration-count: infinite;
    }
    @keyframes next {
        0% {
            transform: translate3d(0, 0, 0);
        }
        50% {
            transform: translate3d(0, -15px, 0);
        }
        from {
            transform: translate3d(0, 0, 0);
        }
    }
</style>
