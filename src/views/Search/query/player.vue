<template>
    <Panel mode="player" :data_api="api" :tag="tag"></Panel>
</template>

<script setup>
import _api from '@/data/api';
import { useRoute, useRouter } from 'vue-router';
import Panel from './panel.vue';
import { provide } from 'vue';
var route = useRoute();
var router = useRouter();
var tag = route.params.tag.toUpperCase();
var api = _api.api.player_api + tag;
provide('go_back', () => router.push('/search/player'));
</script>
