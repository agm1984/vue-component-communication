<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <app-server
                v-for="(server, i) in servers"
                :key="`server-${i}`"
                :server="server"></app-server>
        </ul>
    </div>
</template>

<script>
    import appServer from './Server.vue'

    export default {
        components: {
            'app-server': appServer,
        },
        data: function() {
            return {
                servers: [
                    { id: 1, status: 'Normal' },
                    { id: 2, status: 'Critical' },
                    { id: 3, status: 'Offline' },
                    { id: 4, status: 'Normal' },
                ],
            };
        },
        methods: {
            onShowServerDetails() {
                console.log('KLAJSH')
            },
        },
    };
</script>

<style>

</style>
