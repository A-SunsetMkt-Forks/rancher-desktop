<script lang="ts">
import Vue from 'vue';
export default Vue.extend({ props: { id: { type: String, default: '' } } });
</script>

<template>
  <div
    class="nav-item"
    :data-id="id"
    v-on="$listeners"
  >
    <div
      v-if="$slots.before"
      class="before"
    >
      <slot name="before">
      </slot>
    </div>
    <slot name="default">
      Extensions
    </slot>
    <slot name="after"></slot>
  </div>
</template>

<style scoped lang="scss">
  .nav-item {
    color: var(--body-text);
    text-decoration: none;
    font-size: 1.125rem;
    line-height: 1.75rem;
    padding: 0.5rem 0.75rem;
    display: flex;
    gap: 0.5rem;
    align-items: center;

    &:hover {
      cursor: pointer;
    }
  }

  .before {
    min-width: 1.25rem;
    max-width: 1.25rem;
    display: flex;
    align-items: center;
    justify-content: center;

    img {
      width: 100%;
      height: auto;
    }
  }
</style>
