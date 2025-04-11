<template>
    <div class="flex flex-col justify-start gap-11">
        <GameCountdown  :seconds="state.countdown" />
        <GameText :state="state" />
        <span v-show="!state.completed.value && !state.running.value" class="mx-auto text-[#B0B0B0] text-xl font-mono">{  begynn å skrive  }</span> 
        <div class="m-auto" v-if="state.completed.value || state.running.value">
            <UButton class="cursor-pointer bg-[#B82BFF] hover:bg-[#B82BFF]" @click="reload">Prøv igjen</UButton>
        </div>
    </div>
</template>

<script setup lang="ts">
import GameCountdown from './GameCountdown.vue';
import GameText from './GameText.vue';
import type { useGameState } from './useGameState';

interface Props {
    state: ReturnType<typeof useGameState>;
}

const props = defineProps<Props>();

const reload = () => {
    window.location.reload();
};
</script>