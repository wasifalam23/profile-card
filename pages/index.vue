<script setup>
	import { profile } from '@/profile_data/profile.json';
	import bg from '@/assets/bg-02.jpg';

	const ActivityList = ref([]);

	onMounted(() => {
		const actList = profile.activitySummary
			.split('.')
			.filter((sentence) => sentence.trim() !== '')
			.map((sentence) => sentence.trim() + '.');

		ActivityList.value = actList;
	});

	const openLinkedIn = (url) => {
		window.open(url, '_blank');
	};
</script>

<template>
	<div class="mb-12">
		<header class="bg-white py-3 shadow-sm border-b px-4">
			<div class="max-w-screen-xl mx-auto">
				<div>User Profile</div>
			</div>
		</header>

		<div class="px-4">
			<main
				class="max-w-screen-xl bg-white mx-auto mt-6 rounded-md overflow-hidden shadow-sm border pb-8">
				<div class="h-56">
					<img :src="bg" alt="" class="h-full w-full bg-center" />
				</div>

				<div class="flex items-center justify-center -mt-24">
					<div class="bg-white px-8 py-4 rounded-md w-3/5 shadow-sm border">
						<div class="flex justify-center">
							<div class="w-24 h-24 rounded-md text-center -mt-14">
								<img class="rounded-full" :src="profile.image" alt="" />
							</div>
						</div>

						<div class="flex justify-end">
							<button
								@click="openLinkedIn(profile.linkedInUrl)"
								class="bg-[#0a66c2] hover:bg-[#08529b] text-gray-50 px-3 py-1 rounded-md flex items-center gap-2 text-sm -mt-3 mr-2 font-medium">
								<UIcon name="i-fa6-brands-linkedin" class="text-lg" />
								<span> View on LinkedIn </span>
							</button>
						</div>

						<div
							class="flex flex-col items-center mt-6 mb-4 pb-8 border-b border-dashed border-gray-200">
							<p class="text-2xl font-normal">{{ profile.fullName }}</p>
							<p class="text-gray-700">
								{{ profile.jobTitle }} at
								<span class="text-[#08529b]"> {{ profile.company }} </span>
							</p>
						</div>

						<div class="text-center">
							<p class="text-gray-600 text-sm">
								{{ profile.userSummary }}
							</p>
						</div>
					</div>
				</div>

				<div
					class="bg-white px-8 pt-4 pb-8 rounded-md w-3/5 shadow-sm border mx-auto mt-4">
					<div class="border-b pb-4">
						<h3 class="font-medium text-lg">Activity</h3>
						<ul class="text-gray-600 text-sm mt-2 flex flex-col gap-1">
							<li v-for="(act, index) in ActivityList" :key="index">
								{{ act }}
							</li>
						</ul>
					</div>

					<div class="pt-3">
						<h3 class="font-medium text-lg">Personality</h3>
						<p class="text-gray-600 text-sm mt-2">
							{{ profile.userCharacterAnalysis }}
						</p>
					</div>
				</div>
			</main>
		</div>
	</div>
</template>
