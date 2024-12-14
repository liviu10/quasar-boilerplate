<template>
  <div class="component">
    <div class="component__button">
      <q-btn :color="color" :dense="dense" :label="label" :outline="outline" :round="round" :rounded="rounded"
        :square="square" :text-color="textColor">
      </q-btn>
    </div>
  </div>
</template>

<script setup lang="ts">
interface IComponentButton {
  color?: "primary" | string;
  dense?: boolean;
  label?: string;
  outline?: boolean;
  round?: boolean;
  rounded?: boolean;
  square?: boolean;
  textColor?: "black" | string;
};

withDefaults(defineProps<IComponentButton>(), {
  dense: true,
  label: "Component button"
});
</script>

<style lang="scss" scoped>
@import '../css/fonts.scss';
@import '../css/theme.scss';
@import '../css/utilities.scss';

.component {
  &__button {
    margin: 8px;

    & .q-btn {
      @include roboto-regular();
      border-radius: 0;
      padding: 8px;
      text-transform: capitalize;
      line-height: 0;
      font-size: 16px;
      box-shadow: none;
    }
  }
}
</style>
