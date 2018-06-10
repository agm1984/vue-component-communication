<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">No server selected.</p>
        <p v-else>Server ID: {{ server.id }} Server Status: {{ server.status }}</p>
        <hr>
        <button @click="resetStatus">Change to Normal</button>
    </div>
</template>

<script>
    import { serverBus } from '../../main';

    export default {
        data: function() {
            return {
                server: null,
            };
        },
        methods: {
            resetStatus() {
                this.server.status = 'Normal';
            },
        },
        created() {
            serverBus.$on('serverSelected', (server) => {
                console.log('SERVER ID', server);
                this.server = server;
            });
        },
    };
</script>

<style>

</style>
