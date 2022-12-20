<script setup lang="ts">
import {computed, CSSProperties} from 'vue'
import {resolveAssetUrl} from '@slidev/theme-default/layoutHelper'

const props = defineProps({
  image: {
    type: String,
  },
  backgroundSize: {
    type: String,
  },
})

function handleBackground(background?: string, dim = false, backgroundSize: string = 'cover'): CSSProperties {
  const isColor = background && ['#', 'rgb', 'hsl'].some(v => background.indexOf(v) === 0)

  const style = {
    background: isColor
        ? background
        : undefined,
    color: (background && !isColor)
        ? 'white'
        : undefined,
    backgroundImage: isColor
        ? undefined
        : background
            ? dim
                ? `linear-gradient(#0005, #0008), url(${resolveAssetUrl(background)})`
                : `url("${resolveAssetUrl(background)}")`
            : undefined,
    backgroundRepeat: 'no-repeat',
    backgroundPosition: 'center',
    backgroundSize: backgroundSize,
  };

  if (!style.background)
    delete style.background

  return style
}

const style = computed(() => handleBackground(props.image, false, props.backgroundSize))
</script>

<template>
  <div class="slidev-layout w-full h-full" :style="style">
    <slot />
  </div>
</template>