<script>
	import { browser } from '$app/env';

	import anime from 'animejs';
	import { onMount } from 'svelte';

	onMount(async () => {
		const imageAnimation = anime({
			targets: ['.hero-img-1', '.hero-img-2', '.hero-img-3', '.hero-img-4', '.hero-img-5'],
			translateY: [150, 0],
			easing: 'spring(1, 80, 10, 0)',
			opacity: [0, 1],
			delay: anime.stagger(200, { start: 0 }),
			autoplay: false
		});
		const featureAnimation = anime({
			targets: [
				'.feature-text-1',
				'.feature-text-2',
				'.feature-text-3',
				'.feature-text-4',
				'.feature-text-5'
			],
			scale: [1.5, 1],
			easing: 'spring(1, 80, 10, 0)',
			opacity: [0, 1],
			delay: anime.stagger(200, { start: 1000 }),
			autoplay: false,
			complete: () => {
				console.log('feature text completed');
			}
		});
		anime({
			targets: '.title-text',
			opacity: [0, 1],
			translateY: [50, 0],
			duration: 1000,
			easing: 'easeInOutQuad',
			complete: () => {
				imageAnimation.play();
				featureAnimation.play();
			}
		});
	});
</script>

<section
	class="gap-[20px] w-full h-full bg-immich-bg sm:grid sm:grid-cols-[repeat(12,1fr)] sm:grid-rows-[repeat(12,1fr)] mt-32 sm:mt-0"
>
	<div
		class="title-text max-h-full col-start-5 col-end-9 row-start-2 row-end-5 text-center flex place-items-center flex-col"
	>
		<p class="text-immich-primary text-[64px]">/&#712;imij/</p>
		<p class="max-w-[70%] md:text-base lg:text-2xl xl:text-4xl my-10 font-light">
			An
			<span class="font-bold text-immich-primary">open source</span>, high performance
			<span class="font-bold text-immich-primary">self-hosted</span> backup solution for videos and photos
			on your mobile phone
		</p>

		<a
			href="https://github.com/alextran1502/immich#getting-started"
			target="_blank"
			rel="noreferrer noopener"
		>
			<button
				class="bg-immich-primary text-gray-100 px-6 py-3 rounded-full transition-all hover:bg-immich-primary/90"
				>GETTING STARTED
			</button>
		</a>
	</div>

	<img
		src="/hero-img-1.webp"
		alt="hero-img-mobile-login-screen"
		class="m-auto mt-10 sm:mt-0 sm:block hero-img-1 h-[500px] sm:h-full sm:max-h-full object-contain col-start-2 col-span-2 row-start-2 row-end-5"
	/>

	<img
		src="/hero-img-2.webp"
		alt="hero-img-mobile-home-screen"
		class="m-auto mt-10 sm:mt-0  sm:flex  hero-img-2 h-[500px] sm:h-full sm:max-h-full object-contain col-start-11 col-span-2 row-start-2 row-span-3"
	/>

	<img
		src="/hero-img-3.webp"
		alt="hero-img-web-home-screen"
		class="m-auto mt-10 sm:mt-0  sm:flex hero-img-3 h-full object-contain col-start-9 col-span-full row-start-5 row-end-[8]"
	/>

	<img
		src="/hero-img-4.webp"
		alt="hero-img-mobile-backup-screen"
		class="m-auto mt-10 sm:mt-0  sm:flex hero-img-4 h-[500px] sm:h-full sm:max-h-full object-contain col-start-5 col-span-2 row-start-5 row-span-3"
	/>

	<img
		src="/hero-img-5.webp"
		alt="hero-img-mobile-search-screen"
		class="m-auto mt-10 sm:mt-0  sm:flex hero-img-5 h-[500px] sm:h-full sm:max-h-full object-contain col-start-2 col-span-2 row-start-6 row-span-3"
	/>

	<img
		src="/hero-img-6.webp"
		alt="hero-img-mobile-detail-screen"
		class="m-auto mt-10 sm:mt-0  sm:flex hero-img-6 h-[500px] sm:h-full sm:max-h-full object-contain col-start-10 col-span-2 row-start-[8] row-span-3"
	/>

	<img
		src="/hero-img-7.webp"
		alt="hero-img-web-admin-screen"
		class="m-auto mt-10 sm:mt-0  sm:flex hero-img-7 object-fit col-start-1 col-span-8 row-start-[10] row-span-2"
	/>

	<div
		class="hidden sm:flex feature-text-1 bg-[#d44e3c] text-white font-bold col-start-10 col-span-1 row-start-3 row-span-1 place-items-center place-content-center rounded-[20px] text-center w-[120px] h-[120px]"
	>
		<p>Native <br /> Mobile <br /> App</p>
	</div>

	<div
		class="hidden sm:flex feature-text-2 bg-[#FFB800] text-white font-bold col-start-3 col-span-1 row-start-5 row-span-1 place-items-center place-content-center rounded-[20px] text-center w-[120px] h-[120px]"
	>
		<p>Privacy</p>
	</div>

	<div
		class="hidden sm:flex feature-text-3 bg-[#31A452] text-white font-bold col-start-7 col-end-9 row-start-[8] row-span-1 place-items-center place-content-center rounded-[20px] text-center w-[240px] h-[120px]"
	>
		<p>High Performance <br /> Web App</p>
	</div>

	<div
		class="hidden sm:flex feature-text-4 bg-[#4081EF] text-white font-bold col-start-2 col-span-1 row-start-[9] row-span-2 my-24 place-items-center place-content-center rounded-[20px] text-center "
	>
		<p>Object Detection</p>
	</div>

	<div
		class="hidden sm:flex feature-text-5 bg-[#D183B1] text-white font-bold col-start-10 col-span-1 row-start-[11] row-span-1 place-items-center place-content-center rounded-[20px] text-center"
	>
		<p>Multi-user support <br /> and <br /> User Management</p>
	</div>
</section>
