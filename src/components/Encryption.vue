<template>
    <div class="wrapper">

        <div id="decider" v-if="!decryptView && !encryptView">

            <button class="btn btn-primary btn-raised" @click="encryptView = true">Encrypt</button>

            <hr>

            <button class="btn btn-primary btn-raised" @click="decryptView = true">Decrypt</button>

        </div>

        <div id="decryption" v-if="decryptView">
            <h1>
                Decryption Service
            </h1>
            <form @submit.prevent="runDecryption()">
                <div class="form-group is-empty">
                    <div class="row">
                        <div class="col-sm-10 col-sm-offset-1">
                            <label for="textArea" class="control-label">Vault</label>

                            <textarea class="form-control" rows="3" id="textArea"
                                      v-model="decryptionObject.vault"></textarea>
                            <span class="help-block">
                            We do not store any of this data and never will.
                        </span>
                        </div>
                    </div>
                </div>

                <div class="form-group is-empty">
                    <div class="row">
                        <div class="col-sm-10 col-sm-offset-1">
                            <label class="control-label">Key</label>
                            <input type="text" class="form-control" placeholder="Key" v-model="decryptionObject.key">
                        </div>
                    </div>
                </div>
                <button name="data-encryption-button" class="btn btn-primary">Decrypt</button>
            </form>
        </div>
        <div id="encryption" v-if="encryptView">
            <h1>
                Encryption Service
            </h1>
            <form @submit.prevent="runEncryption()">
                <div class="form-group is-empty">
                    <div class="row">
                        <div class="col-sm-10 col-sm-offset-1">
                            <label for="textArea" class=" control-label">Encryption Message</label>

                            <textarea class="form-control" rows="3" id="textArea"
                                      v-model="encryptionObject.data"></textarea>
                            <span class="help-block">
                            We do not store any of this data and never will.
                        </span>
                        </div>
                    </div>
                </div>

                <div class="form-group">
                    <div class="row">
                        <div class="col-sm-10 col-sm-offset-1">
                            <label for="ttl" class="control-label">Time until expire</label>

                            <select id="ttl" class="form-control">
                                <option>1 Hour</option>
                                <option>2 Hours</option>
                                <option>3 Hours</option>
                                <option>4 Hours</option>
                                <option>5 Hours</option>
                            </select>
                        </div>
                    </div>
                </div>
                <button name="data-encryption-button" class="btn btn-primary">Encrypt</button>
            </form>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import moment from 'moment';
    import $ from 'jquery';
    require('snackbarjs');
    require('bootstrap-material-design')

    export default {
        name: 'encryption',
        data () {
            return {
                decryptView: false,
                encryptView: false,
                encryptionObject: {
                    data: null,
                    ttl: 30,
                },
                decryptionObject: {
                    key: '',
                    vault: '',
                },
            }
        },

        methods: {
            runEncryption() {
                let self = this;

                axios.post('http://localhost:7014/', this.encryptionObject).then(
                    function (response) {
                        self.decryptView = true;
                        self.encryptView = false;
                        self.decryptionObject = response.data;
                        $.snackbar({
                            content: "Successful encryption, it's like you've done this before...",
                            style: "snackbar-success",
                            timeout: 5000,
                        });
                    }
                ).catch(
                    function (errors) {
                        $.snackbar({
                            content: "Somethings gone wrong, please try again",
                            style: "snackbar-danger",
                            timeout: 5000,
                        });
                    }
                )
            },

            runDecryption() {
                let self = this;

                axios.post('http://localhost:7014/decrypt', this.decryptionObject).then(
                    function (response) {
                        self.decryptView = false;
                        self.encryptView = true;
                        self.encryptionObject = response.data;
                        $.snackbar({
                            content: "Successful decryption, it's like you've done this before...",
                            style: "snackbar-success",
                            timeout: 5000,
                        });
                    }
                ).catch(
                    function (errors) {

                        $.snackbar({
                            content: "Somethings gone wrong, please try again",
                            style: "snackbar-danger",
                            timeout: 5000,
                        });
                    }
                )
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h1 {
        margin-top: 0;
        padding-top: 20px;
    }

    #decider > .btn {
        font-size: 42px;
    }

    .form-label {
        color: #ffffff;
    }
</style>
