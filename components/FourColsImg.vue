<script setup></script>

<template>
    <div :class="$style.col4img">
        <slot />
    </div>
</template>

<style lang="postcss" module>
.col4img {}

.col4img > ul {
    @apply grid grid-cols-4 gap-4 px-4;
}

.col4img > ul > li {
    @apply flex flex-col justify-center items-center gap-2;
}

.col4img > ul > li p :not(img) {
    @apply text-4 text-gray-400;
}
</style>