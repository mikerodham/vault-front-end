<template>
    <div id="app">
        <div class="container">
            <div class="vault-wrapper row equal">
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
                        <div id="flex-container">
                            <div id="flex-item-app"><encryption></encryption></div>
                        </div>
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

    #snackbar-container {
        position: fixed;
        bottom: 0;
        left: 20px;
    }

    .snackbar-success {
        background: #2e9237;
        color: #ffffff;
    }

    .snackbar-danger {
        background: #921f18;
        color: #ffffff;
    }

    body, html {
        height: 100%;
    }
    body {
        padding-top: 0;
        margin-top: 0;
    }

    #flex-container {
        display: -webkit-box;      /* OLD - iOS 6-, Safari 3.1-6 */
        display: -moz-box;         /* OLD - Firefox 19- (buggy but mostly works) */
        display: -webkit-flex;     /* NEW - Chrome */
        display: flex;             /* NEW, Spec - Opera 12.1, Firefox 20+ */
        -webkit-box-flex-direction: row;
        -moz-box-flex-direction: row;
        -webkit-flex-direction: row;
        flex-direction: row;
        height:100%;
    }

    #flex-item {
        margin: auto;
        height:auto;
        width:auto;
    }

    #flex-item-app {
        margin: auto;
        height:auto;
        width:100%;
    }


    .vault-wrapper.row [class*='col-']:first-child {
        padding-right: 0;
    }
    .vault-wrapper.row [class*='col-']:last-child {
        padding-left: 0;
    }

    .equal {
        display: flex;
        display: -webkit-flex;
    }

    html, body {
        height: 100%;
    }

    body {
        background: #666;
        color: #000000;
    }

    .vault {
        background: #fff;
        height: 100%;
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
