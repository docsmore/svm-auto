<script lang="ts">
import { defineComponent } from 'vue';
import { mapStores } from 'pinia';
import { useRootStore } from '@/stores/root.store';
import { useUIStore } from '@/stores/ui.store';

export default defineComponent({
	computed: {
		...mapStores(useRootStore, useUIStore),
		basePath(): string {
			return this.rootStore.baseUrl;
		},
		logoPath(): string {
			return this.basePath + this.uiStore.logo;
		},
	},
});
</script>

<template>
	<img />
</template>

<style lang="scss" module>
.img {
	height: 82px;
	src: url('https://res.cloudinary.com/dqql2wlbt/image/upload/v1726183681/Transparent-02_ummxaa.png');
}
</style>
