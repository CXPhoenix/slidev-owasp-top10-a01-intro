<script setup></script>

<template>
    <div :class="$style.col3img">
        <slot />
    </div>
</template>

<style lang="postcss" module>
.col3img {}

.col3img > ul {
    @apply grid grid-cols-3 gap-4;
}

.col3img > ul > li {
    @apply flex flex-col justify-center items-center gap-2;
}

.col3img > ul > li p :not(img) {
    @apply text-4 text-gray-400;
}
</style>