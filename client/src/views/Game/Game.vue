<template>
	<div class="bg-[#2C2C2C] flex flex-col w-full h-full">
        <Navigation class="px-32 pt-8" />
        <div class="flex flex-col p-32 justify-center">
            <div class="flex justify-center w-full container">
                <GameOver v-if="state.completed.value" :state="state" />
                <GamePlaying v-else :state="state" />
            </div>
        </div>
	</div>
</template>

<script setup lang="ts">
import Navigation from '../../components/Navigation.vue';
import { useGameState } from './useGameState';
import GameOver from './GameOverAnimation.vue';
import GamePlaying from './GamePlaying.vue';

const state = useGameState();

const reload = () => {
  window.location.reload();
};
</script>
