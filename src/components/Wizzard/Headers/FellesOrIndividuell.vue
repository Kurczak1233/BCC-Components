<script setup>
import UsersGroup from "../../icons/UsersGroup.vue";
import UserIcon from "../../icons/UserIcon.vue";
import CheckIcon from "../../icons/CheckIcon.vue";
const props = defineProps({
  componentTitle: String,
  isGroup: Boolean,
  checked: Boolean,
  possibleItems: Number,
  maxItems: Number,
  extraInfo: String,
});
</script>

<template>
  <div
    :class="
      props.checked
        ? `${'border-2 border-solid border-prime-200 w-6/12 mr-4 ml-4 p-4 bg-alt-200 rounded-lg'}`
        : `w-6/12 mr-4 p-4 bg-alt-200 rounded-lg`
    "
  >
    <div class="flex items-center justify-between">
      <div class="flex items-center">
        <div class="text-small-medium font-semibold font-sans">
          {{ props.componentTitle }}
        </div>
        <UsersGroup v-if="props.isGroup" class="ml-2.5" />
        <UserIcon class="ml-2.5" v-else />
      </div>
      <div>
        <CheckIcon v-show="props.checked" />
      </div>
    </div>
    <div class="flex items-center justify-between mt-2">
      <div class="text-small-medium font-sans font-normal font-sans">
        {{ props.possibleItems }} / {{ props.maxItems }}
      </div>
      <div class="text-small-medium font-sans font-normal font-sans opacity-50">
        {{ props.extraInfo }}
      </div>
    </div>
  </div>
</template>
<style scoped>
.text-small-medium {
  font-size: 15px;
}
</style>
