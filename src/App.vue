<script setup lang="ts">
import { onMounted } from 'vue'
import { storeToRefs } from 'pinia'
import { RouterLink, RouterView } from 'vue-router'
import { useDeliveryStore } from './store'
const store = useDeliveryStore()
const { approvedShare, offers, urgent } = storeToRefs(store)
onMounted(store.load)
</script>

<template><div class="shell"><aside><div class="brand">NatureCreditsEU<span>NATURE-POSITIVE FINANCE</span></div><nav><RouterLink to="/">Credit schemes</RouterLink><RouterLink to="/insights">Integrity guidance</RouterLink></nav><div class="health"><i /> Java nature credit investment service connected</div></aside><main><header><div><span class="eyebrow">Mobilise high-integrity finance for nature restoration</span><h1>Nature Credit Investment Desk</h1></div><button @click="store.addOffer">Add credit scheme</button></header><section class="summary"><article><small>Schemes ready</small><strong>{{ approvedShare }}%</strong><div class="bar"><span :style="{ width: `${approvedShare}%` }" /></div></article><article><small>Schemes tracked</small><strong>{{ offers.length }}</strong><p>Shared investment view</p></article><article><small>High-priority gaps</small><strong>{{ urgent }}</strong><p>Needs attention</p></article></section><RouterView /></main></div></template>
