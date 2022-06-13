<script setup lang="ts">
import { computed } from 'vue'

type Headings = 'h1' | 'h2' | 'h3' | 'h4' | 'h5' | 'h6'
type Text = 'p' | 'span'
type Image = 'img'

const { type } = defineProps<{
    type: Headings | Text | Image
}>()

const isImage = computed(() => type === 'img')
const isHeading = computed(() => ['h1', 'h2', 'h3', 'h4', 'h5', 'h6'].includes(type))
</script>

<template>
    <template v-if="isImage">
        <div class="object-contain flex-shrink-0">
            <div class="h-full w-full rounded-full bg-gray-300 animate-pulse" />
        </div>
    </template>

    <template v-else>
        <component :is="type" :class="[isHeading ? 'h-6 w-[250px]' : 'h-4 w-full ', 'block bg-gray-300 animate-pulse']" />
    </template>
</template>
