<template>
       <div class="wrapper">
            <span v-for="star in totalRating" :key="star" class="star" :class="{ filled: star <= value }" @click="enabled ? setRating(star) : null">★</span>
        </div>
</template>

<script lang="ts" setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps<{
  value: number;
  totalRating: number;
  enabled: boolean;
}>();

const emit = defineEmits<(event: "update-rating", value: number) => void>();

const setRating = (star: number) => {
  emit("update-rating", star);
};

</script>

<style lang="css"  src="@/assets/starRaiting.css" scoped>
</style>

