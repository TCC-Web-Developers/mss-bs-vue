<script>
const baseClass = 'btn';
const variantButton = ['soft', 'ghost', 'outline'];

const _props = {
    theme: {
        type: String,
        default: '',
    },
    active: {
        type: Boolean,
        default: false,
    },
    size: {
        type: String,
        default: '',
    },
    elevate: {
        type: Boolean,
        default: false,
    }
}

variantButton.map(variant => {
    _props[variant] = {
            type: Boolean,
            default: false,
        }
})

export default {
    props: _props,
    setup(props) {

        const styleClass = reactive({});
        const hasTheme = computed(() => {
            return props.theme.trim() != '';
        });


        let hasVariant = false;

        variantButton.map(variant => {
            if (props[variant] && hasTheme) {
                let variantStyleName = `${baseClass}-${variant}-${props.theme}`;
                styleClass[variantStyleName] = true;
                hasVariant = true;
            }
        })

        if (!hasVariant && hasTheme) {
            let themeClass = baseClass + '-' + props.theme.trim();
            styleClass[themeClass] = true;
        }


        return {
            styleClass
        }
  
    }
}
</script>

<!--<script setup>
const props = defineProps({
    theme: {
        type: String,
        default: '',
    },
    active: {
        type: Boolean,
        default: false,
    },
    size: {
        type: String,
        default: '',
    },
    outline: {
        type: Boolean,
        default: false,
    },

    soft: {
        type: Boolean,
        default: false,
    },
});

const baseClass = 'btn';

const styleClass = reactive({});

const hasTheme = computed(() => {
    return props.theme.trim() != '';
});

if (props.soft && hasTheme) {
    let outlineStyle = baseClass + '-soft-' + props.theme.trim();
    styleClass[outlineStyle] = true;
} else if (props.outline && hasTheme) {
    let outlineStyle = baseClass + '-outline-' + props.theme.trim();
    styleClass[outlineStyle] = true;
} else {
    if (hasTheme) {
        let themeClass = baseClass + '-' + props.theme.trim();
        styleClass[themeClass] = true;
    }
}
</script>
-->

<template>
    <button
        class="btn"
        :type="Object.hasOwn($attrs, 'type') ? $attrs.type : 'button'"
        :class="{
            disabled:
                Object.hasOwn($attrs, 'disabled') && $attrs.disabled != 'false',
            active: active,
            ...styleClass,
        }"
        :aria-disabled="
            Object.hasOwn($attrs, 'disabled') && $attrs.disabled != 'false'
                ? true
                : null
        "
    >
        <slot></slot>
    </button>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/components/buttons';
</style>
