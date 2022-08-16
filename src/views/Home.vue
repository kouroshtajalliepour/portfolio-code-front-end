<script>
import AppBanner from '@/components/shared/AppBanner';
import ProjectSingle from '../components/projects/ProjectSingle2.vue';
export default {
	name: 'Home',
	data(){
		return{
			projects: [
				{
					id: 1,
					title: 'Swan Agency',
					category: 'Advertisement Agency',
					linkto: "https://swanagc.com",
					img: require('@/assets/images/swanagc.jpg'),
				},
				{
					id: 2,
					title: 'Web Clicks',
					linkto: "https://webclicks.ir",
					category: 'Development Agenecy',
					img: require('@/assets/images/webclicks.jpg'),
				},
			]
		}
	},
	components: {
		AppBanner,
		ProjectSingle
	},
};
</script>

<template>
	<div class="container mx-auto">
		<!-- Banner -->
		<AppBanner class="mb-5 sm:mb-8" />

		<!-- Projects -->

		<div class="text-center">
			<p
				class="font-general-semibold text-2xl sm:text-5xl font-semibold mb-2 text-ternary-dark dark:text-ternary-light"
			>
				Organizations
			</p>
		</div>

		<div class="mt-10 sm:mt-10">
			<h3
				class="font-general-regular
					text-center text-secondary-dark
					dark:text-ternary-light
					text-md
					sm:text-xl
					font-normal
					mb-4
				"
			>
				Check out my Organizations !
			</h3>
		</div>

		<div
			class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-2 mt-6 sm:gap-10"
		>
			<ProjectSingle
				v-for="project in projects"
				:key="project.id"
				:project="project"
			/>
		</div>
	</div>
</template>

<style scoped></style>
