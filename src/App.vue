<template>
    <div id="app">
        <div class="container">
            <div class="vault-wrapper row">
                <div class="col-sm-4">
                    <div class="gutter">
                        <h1>The Vault</h1>

                        <p>
                            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Atque, cum est, eum exercitationem
                             hic labore natus nesciunt nihil omnis porro praesentium quidem rem sequi similique,
                              sint tempora temporibus voluptatem voluptatibus?

                              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Atque, cum est, eum exercitationem
                             hic labore natus nesciunt nihil omnis porro praesentium quidem rem sequi similique,
                              sint tempora temporibus voluptatem voluptatibus?
                        </p>
                    </div>
                </div>
                <div class="col-sm-8">
                    <div class="vault">
                        <encryption></encryption>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import material from 'bootstrap-material-design'
    $.material.init()
    export default {
        name: 'app'
    }
</script>

<style>
    @import url('./assets/css/bootstrap-material-design.min.css');

    .vault-wrapper.row [class*='col-']:first-child {
        padding-right: 0;
    }
    .vault-wrapper.row [class*='col-']:last-child {
        padding-left: 0;
    }

    body {
        background: #666;
        color: #000000;
        padding-top: 30px;
    }

    .vault {
        background: #fff;
    }

    p {
        color: #000000;
    }

    .card {
        height: auto;
    }

    .card .col-sm- * {
        height: 100%;
    }

    .gutter {
        text-align: left;
        line-height: 1.7;
        background-color: #F00;
        height: 100%;
        padding: 30px;
    }

    .gutter > h1 {
        margin-bottom: 30px;
        margin-top: 0;
    }

    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
    }
</style>
