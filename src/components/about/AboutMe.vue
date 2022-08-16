<script>
import Button from '../reusable/Button.vue';
import HireMeModal from '../HireMeModal.vue';
export default {
	components: {
		Button,
		HireMeModal,
	},
	
	data(){
		return{
			modal: false,
			profileImage: require('@/assets/images/kourosh-mockup.jpg')

		}
	},
	methods: {
		showModal() {
			if (this.modal) {
				// Stop screen scrolling
				document
					.getElementsByTagName('html')[0]
					.classList.remove('overflow-y-hidden');
				this.modal = false;
			} else {
				document
					.getElementsByTagName('html')[0]
					.classList.add('overflow-y-hidden');
				this.modal = true;
			}
		},
	},
	async created(){
		// todo: API CALL
	},
	setup() {
		return {
			bios: [
				{
					id: 1,
					bio:
						"Before i get introduced to programming, I had some expiriences working as an english teacher in a local insitute when i was a teenager and also as an accountant in Iran Abacus Accounting company (my last role was head of the purchase order department) then i got introduced to programming and did nothing else but development afterwards. Now I'm a senor full-stack developer specialiezed mostley in back-end development and also a development coach."
				},
				{
					id: 2,
					bio:
						"I started my development team named Web Clicks in August 2021 with my best students and became an entrepreneur, and later in early 2022 i started Swan Agency (my advertisement company). We are are always open to communicate in both Swan Agency & Web Clicks and also I'm always opent to new ideas for business.",
				},
			],
		};
	},
};
</script>

<template>
	<div class="block sm:flex sm:gap-10 mt-10 sm:mt-20">
		<!-- About profile image -->
		<div class="w-full sm:w-1/4 mb-7 sm:mb-0">
			<img
				:src="profileImage"
				class="rounded-xl w-96"
				alt=""
			/>
		</div>

		<!-- About details -->
		<div class="w-full sm:w-3/4 text-left">
			<p
				v-for="bio in bios"
				:key="bio.id"
				class="font-general-regular mb-4 text-ternary-dark dark:text-ternary-light text-lg"
			>
				{{ bio.bio }}
				
			</p>
			<Button
					
						title="Lets talk"
						class="text-md font-general-medium bg-indigo-500 hover:bg-indigo-600 text-white shadow-sm rounded-md px-5 py-2.5 duration-300"
						@click="showModal()"
						aria-label="Hire Me Button"
					/>
		</div>
		<HireMeModal
			:showModal="showModal"
			:modal="modal"
			:categories="categories"
			aria-modal="Hire Me Modal"
		/>
	</div>
</template>
