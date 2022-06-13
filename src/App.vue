<template>
    <div class="min-h-screen bg-[#eee] grid place-items-center">
        <Suspense>
            <ProfileCard />

            <template #fallback>
                <ProfileCardSkeleton />
            </template>
        </Suspense>
    </div>
</template>

<script setup lang="ts">
import ProfileCard from './components/ProfileCard.vue'
import ProfileCardSkeleton from './components/ProfileCardSkeleton.vue'
</script>
