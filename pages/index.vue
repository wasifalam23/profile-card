<script setup>
	import bg from '@/assets/bg-02.jpg';
</script>

<template>
	<div class="">
		<header class="bg-white py-3 shadow-sm border-b">
			<div class="max-w-screen-xl mx-auto px-4">
				<div>Logo</div>
			</div>
		</header>

		<div class="px-4">
			<main
				class="max-w-screen-xl mx-auto mt-6 rounded-md overflow-hidden shadow-sm border pb-6">
				<div class="h-56">
					<img :src="bg" alt="" class="h-full w-full bg-center" />
				</div>

				<div class="flex items-center justify-center -mt-24">
					<div class="bg-white px-8 py-4 rounded-md w-3/5 shadow-sm border">
						<div class="flex justify-center">
							<div class="w-24 h-24 rounded-md text-center -mt-14">
								<img
									class="rounded-full"
									src="https://mighty.tools/mockmind-api/content/human/75.jpg"
									alt="" />
							</div>
						</div>

						<div class="flex justify-end">
							<button
								class="bg-blue-700 text-gray-50 px-2 py-1 rounded-md flex items-center gap-2 hover:bg-blue-800">
								<UIcon name="i-fa6-brands-linkedin" class="text-lg" />
								<span> Visit LinkedIn Profile </span>
							</button>
						</div>

						<div class="flex flex-col items-center mt-4">
							<p class="text-xl font-medium">Tom Brown</p>
							<p>Associate Director at Wayne EnterPrises</p>
						</div>
					</div>
				</div>
			</main>
		</div>
	</div>
</template>
