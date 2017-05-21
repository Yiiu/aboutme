<template>
    <section class="container info" :class="{start: start}">
        <div class="logo">
            <Logo />
        </div>
        <h2 class="title">Yiiu</h2>
        <p class="description" >front end</p>
        <Next></Next>
    </section>
</template>
<script>
    import Logo from '~components/Logo.vue'
    import Next from '~components/Next.vue'
    export default {
        components: {
            Logo,
            Next
        },
        props: ['start']
    }
</script>
<style lang="less">
    .container.info {
        .logo {
            width: 10vw;
            min-width: 40px;
            max-width: 90px;
            transition: 1.3s all cubic-bezier(0.86, 0, 0.07, 1);
            transition-delay: .1s;
            opacity: 0;
        }
        h2.title {
            font-size: 2.3em;
            font-weight: 400;
            margin-top: 18px;
            transition: 1.3s all cubic-bezier(0.86, 0, 0.07, 1);
            transition-delay: .3s;
            opacity: 0;
            transform: translate3d(0, -25px, 0);
        }
        p.description {
            color: #717171;
            transition: 1s all cubic-bezier(0.86, 0, 0.07, 1);
            transition-delay: .7s;
            opacity: 0;
            transform: translate3d(0, -15px, 0);
        }
        .next {
            transition: 1s all cubic-bezier(0.86, 0, 0.07, 1);
            opacity: 0;
            transform: translate3d(0, -15px, 0);
        }
    }
    .container.info.start {
        .logo {
            opacity: 1;
        }
        h2.title {
            opacity: 1;
            transform: translate3d(0, 0, 0);
        }
        p.description {
            opacity: 1;
            transform: translate3d(0, 0, 0);
        }
        .next {
            opacity: 1;
            transform: translate3d(0, 0, 0);
        }
    }
</style>
