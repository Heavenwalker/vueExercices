<template>

    <li class="list-group-item" style="cursor:pointer" @click="serverSelected">
        Server #{{ server.id }} 
    </li>    
  
</template>

<script>
import {serverBus} from '../../main.js'
export default{
    props:['server'],
    methods: {
        serverSelected(){
            
            serverBus.$emit('serverSelect', this.server)
            
        }
    }
}
</script>

<style>

</style>
