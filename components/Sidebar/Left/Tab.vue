<template>
    <NuxtLink to="#" class="flex items-center p-3 w-min hover:bg-gray-200 rounded-full text-black dark:hover:bg-dim-200 dark:text-white" :class="defaulTransition">
        <div class="w-6 h-6 text-dark">
            <slot name="icon"></slot>
        </div>
        <div class="ml-4 text-xl hidden xl:block" :class="textClasses">
            <slot name="name"></slot>
        </div>
    </NuxtLink>
</template>

<script setup>
const { defaulTransition } = useTailwindConfig();
const props = defineProps({
    active: {
        type: Boolean,
        default: false
    }
})

const textClasses = computed(() => props.active ? "font-semibold" : "font-normal")
</script>