<script setup lang="ts">
import { computed } from 'vue'
import { handleBackground } from '../layoutHelper'

const props = defineProps({
    background: {
        default: './theme/images/Camunda_Desktop-Wallpaper_Black.png'
    },
})

const style = computed(() => handleBackground(props.background, true))
</script>

<template>
    <div class="slidev-layout cover" :style="style">
        <div class="absolute top-30">
            <div><slot name="title" /></div>
            <div id="grid3" grid="~ cols-3 gap-x-3" m="-t-2" prose class="text-black">
                                <slot name="left" />
                
                <div class="text-center bg-blue/52 border-(~ rounded-lg gray-400)"><br>
                    <slot name="center" />
                </div>
                <div class="text-center bg-blue/52 border-(~ rounded-lg gray-400)"><br>
                    <slot name="right" />
                </div>
            </div>
        </div>    
    </div>
</template>