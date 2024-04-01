<script>
import { RouterLink } from 'vue-router';
export default {
    props:{
        ...RouterLink.props
    },
    computed:{
        isExternal(){
            return typeof this.to === 'string' && this.to.startsWith('http');
        }
    }
}
</script>
<template>
    <a 
        v-if="isExternal"
        :href="to" 
        class="external-link"
        target="_blank" 
        rel="noopener noreferrer"
    ><slot /></a>
    <router-link v-else v-bind="$props"><slot/></router-link>
</template>