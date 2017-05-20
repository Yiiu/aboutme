<template>
    <section class="container">
        <div class="logo">
            <Logo />
        </div>
        <h2 class="title">Yiiu</h2>
        <p class="description" >front end</p>
        <Next />
    </section>
</template>
<script>
    import Logo from '~components/Logo.vue'
    import Next from '~components/Next.vue'
    export default {
        components: {
            Logo,
            Next
        }
    }
</script>
<style lang="less" scoped>
    p.description {
        color: #717171;
    }
    .logo {
        width: 10vw;
        min-width: 40px;
        max-width: 90px;
    }
    h2.title {
        font-size: 2.3em;
        font-weight: 400;
        margin-top: 18px;
    }
</style>
