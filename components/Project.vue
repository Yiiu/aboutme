<template>
    <section class="container">
        <h1 class="title">Project</h1>
        <section class="project-item">
            <div v-for="(item, index) in project">
                <a :href="pr.link" class="list" target="_blank" v-for="pr in item">
                    <div class="info">
                        <h2 class="name">{{pr.name}}</h2>
                        <div class="description">{{pr.description}}</div>
                    </div>
                </a>
            </div>
        </section>
    </section>
</template>
<script>
    export default {
        data () {
            return {
                project: [
                    [
                        {
                            name: 'Everyone',
                            description: '🍊Ant Design UI library for Vuejs 2.0',
                            link: 'https://github.com/Yiiu/everyone'
                        },
                        {
                            name: 'Eel',
                            description: '🍋 vuejs',
                            link: 'https://github.com/Yiiu/eel'
                        }
                    ],
                    [
                        {
                            name: 'Fishy',
                            description: '🍉 mongoose reactjs express blog',
                            link: 'https://github.com/fishying/fishy'
                        },
                        {
                            name: 'Soap',
                            description: '🍑 nuxt.js mongodb express',
                            link: 'https://github.com/everySoap/Soap'
                        }
                    ]
                ]
            }
        }
    }
</script>
<style lang="less">
h1.title {
    position: absolute;
    top: 120px;
    font-size: 2.4em;
    font-weight: 400;
}
.project-item {
    display: flex;
    justify-content: center;
    flex-flow: wrap;
    max-width: 1230px;
    width:100%;
    >div {
        display: flex;
        margin-right: 10px;
        flex-wrap: wrap;
        @media screen and (max-width: 1230px) {
            margin-right: 10px !important;
            margin-left: 10px;
            margin-bottom: 10px;
            &:last-child {
                margin-right: 0;
            }
        }
        @media screen and (max-width: 630px) {
            .list {
                margin-left: 10px;
                margin-right: 10px !important;
                &:first-child {
                    margin-bottom: 10px;
                }
            }
        }
        &:last-child {
            margin-right: 0;
        }
        a {
            color: #000;
            text-decoration: none;
        }
        .list {
            width: 300px;
            flex-grow: 1;
            flex-shrink: 0;
            border: 1px solid #d8d8d8;
            border-radius: 1px;
            padding: 24px;
            margin-right: 10px;
            flex-basis: 300px;
            transition: .3s border;
            h2.name {
                margin-bottom: 12px;
            }
            &:last-child {
                margin-right: 0;
            }
            &:hover {
                border-color: #000;
            }
        }
    }
}
</style>
