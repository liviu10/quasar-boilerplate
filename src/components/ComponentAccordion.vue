<template>
  <div class="component">
    <div class="component__accordion">
      <q-list>
        <q-expansion-item :dense="dense" :expand-separator="expandSeparator" :icon="icon" :label="label">
          <q-card>
            <q-card-section>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
              commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
              eveniet doloribus ullam aliquid.
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>
    </div>
  </div>
</template>

<script setup lang="ts">
interface IComponentAccordion {
  dense?: boolean
  expandSeparator?: boolean
  icon?: string
  label?: string
};

withDefaults(defineProps<IComponentAccordion>(), {
  dense: true,
  expandSeparator: false,
  label: "Component accordion",
});
</script>

<style lang="scss" scoped>
@import '../css/fonts.scss';
@import '../css/theme.scss';
@import '../css/utilities.scss';

.component {
  &__accordion {
    width: 600px;

    & .q-list {
      @include roboto-regular();

      & .q-expansion-item {
        padding: 8px;

        &:deep() {
          & .q-item {
            margin-top: 8px;
            margin-bottom: 8px;
            padding: 0;

            &__label {
              font-size: 18px;
              user-select: none;
            }
          }
        }

        & .q-card {
          &__section {
            padding: 0;
            font-size: 16px;
          }
        }
      }
    }
  }

  @media screen and (max-width: 599px) {
    &__accordion {
      width: 100%;
    }
  }
}
</style>
