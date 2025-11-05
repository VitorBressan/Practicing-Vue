<template>
    <button
        :type="props.type"
        :class="[
            'inline-flex items-center justify-center gap-2 px-4 py-2 rounded-md font-medium transition-transform duration-150 focus:outline-none focus:ring-2 focus:ring-offset-2',
            'bg-linear-gradient-to-r from-indigo-600 to-blue-500  hover:from-indigo-700 hover:to-blue-600',
            'shadow-sm hover:shadow-md active:scale-95',
            props.disabled ? 'opacity-50 cursor-not-allowed filter grayscale' : '',
            props.extraClass
        ]"
        :disabled="props.disabled"
        @click="handleClick"
    >
        <template v-if="$slots.icon">
            <slot name="icon" />
        </template>
        <span v-if="props.label" class="text-black">{{ props.label }}</span>
        <template v-else-if="$slots.default">
            <slot />
        </template>
    </button>
</template>

<script setup>
const props = defineProps({
    label: { type: String, default: '' },
    extraClass: { type: [String, Array, Object], default: '' },
    type: { type: String, default: 'button' },
    disabled: { type: Boolean, default: false },
    // opcional: passar função diretamente via prop
    onClick: { type: Function, default: null }
})

const emit = defineEmits(['click'])

function handleClick(e) {
    if (props.disabled) return
    if (typeof props.onClick === 'function') props.onClick(e)
    emit('click', e)
}
</script>