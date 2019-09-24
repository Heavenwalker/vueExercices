<template>
    <div class="col-xs-12 col-sm-6">
        <p>Server Details are currently not updated</p>
        <p v-if='!server'>NO SERVER SELECTED</p>
        <p v-else>Server #{{ server.id }} selected, Status: {{ server.status }}</p>
        <button @click="setNormal">Return to Normal</button>
    </div>

</template>

<script>
    import {serverBus} from '../../main.js';
    export default{
        data: function() {
            return{
                server: null
            }
        },
        methods:{
            setNormal(){
                this.server.status='Normal'
                
            }
        },
        created(){
            serverBus.$on('serverSelect',(server) => {
                            this.server = server;
                        })
        }
}
</script>

<style>

</style>
