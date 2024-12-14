<template>
  <div class="component">
    <div class="component__card">
      <q-card :bordered="bordered" :square="square">
        <q-card-section>
          {{ label }}
        </q-card-section>

        <q-card-section v-if="content">
          {{ content }}
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script setup lang="ts">
interface IComponentCard {
  bordered?: boolean
  content?: string
  label?: string
  square?: boolean
};

withDefaults(defineProps<IComponentCard>(), {
  bordered: true,
  label: "Component card",
  square: false,
});
</script>

<style lang="scss" scoped>
@import '../css/fonts.scss';
@import '../css/theme.scss';
@import '../css/utilities.scss';

.component {
  &__card {
    width: 600px;

    & .q-card {
      &__section {
        @include roboto-regular();
        padding-top: 8px;
        padding-bottom: 8px;

        &:first-child {
          font-size: 18px;
          text-align: center;
        }

        &:last-child {
          font-size: 16px;
        }
      }
    }
  }

  @media screen and (max-width: 599px) {
    &__card {
      width: 100%;
    }
  }
}
</style>
