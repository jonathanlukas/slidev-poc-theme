<script setup lang="ts">
import { computed } from 'vue'
import { handleBackground } from '../layoutHelper'

const props = defineProps({
    background: {
        default: '../images/left-orange-square.png',
    },
})

const style = computed(() => handleBackground(props.background, false))
</script>

<template>
    <div class="slidev-layout cover" :style="style">
        <div class="absolute top-10 right-19 text-black">
            <slot />
        </div>
    </div>
</template>