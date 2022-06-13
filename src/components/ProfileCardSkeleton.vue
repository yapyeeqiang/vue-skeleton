<script setup lang="ts">
import SkeletonItem from './SkeletonItem.vue'
</script>

<template>
    <div class="flex items-start space-x-4 bg-white p-8 max-w-2xl mx-auto rounded-xl w-full">
        <SkeletonItem type="img" class="h-24 w-24" />

        <div class="space-y-2 flex-1">
            <SkeletonItem type="span" />
            <SkeletonItem type="h3" />
            <SkeletonItem type="p" />
        </div>
    </div>
</template>
