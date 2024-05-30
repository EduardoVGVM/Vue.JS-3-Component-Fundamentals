<script setup>
import { ref } from 'vue';
import CoffeePlan from './CoffeePlan.vue'

const plans = ref(["The Single", "The Curious", "The Addict", "The Hacker"])

const selectedCoffeePlan = ref()
function handleSelectCoffePlan(name) {
    selectedCoffeePlan.value = name
}

const plansWrapper = ref();
</script>

<template>
    <div ref="plansWrapper" class="plans">
        <CoffeePlan v-for="plan in plans" :key="plan" :name="plan" :selected="plan === selectedCoffeePlan"
            @click="handleSelectCoffePlan(plan)">
        </CoffeePlan>
    </div>
</template>