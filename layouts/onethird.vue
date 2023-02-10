<script setup lang="ts">
import { computed } from 'vue'
import { handleBackground } from '../layoutHelper'

const props = defineProps({
    imageLeft: {
        default: './theme/images/left-orange-yellow.png',
        type: String
    },
    class: {
        type: String,
    },
})

const left = computed(() => handleBackground(props.imageLeft, true))
</script>

<template>
    <div class="grid grid-cols-3 wfull hfull gap-x-7">
        <div class="ml-14 my-14" :style="left"></div>
        <div class="ml-14 my-14 span-2 bg-white" :class="props.class">
            
                <slot />
            
        </div>      
    </div>
</template>