<script>
	import LocomotiveScrollProvider from 'svelte-locomotive-scroll';
	import 'locomotive-scroll/src/locomotive-scroll.scss';
	import Logo from '$lib/image/Logo4.svg';
	import { page } from '$app/stores';
	import '../app.css';
	import Icon from '@iconify/svelte';
	import { menu } from '../store.js';

	function decrement() {
		menu.update((menu) => (menu = !menu));
	}
</script>

<LocomotiveScrollProvider
	options={{
		smooth: true,
		smoothMobile: false,
		getDirection: true,
		getSpeed: true,
		inertia: 0.7
	}}
	watch={$page}
	location={$page.url}
	onLocationChange={(scroll) => scroll.scrollTo(0, { duration: 2, disableLerp: false })}
	imageTarget={'.grid-item-media'}
>
	<header
		data-scroll-section
		class:active2={$page.url.pathname === '/stocks'}
		class="bg-white relative "
	>
		<div class="xl:mx-32 lg:mx-10 sm:mx-8  mx-4 pt-5 flex justify-between sm:items-center">
			<a href="/" class="flex z-20 items-center">
				<img class="w-48 sm:w-52" src={Logo} alt="" />
			</a>
			<div class="pt-2">
				<ul class="lg:flex hidden gap-8 font-medium">
					<a class:active={$page.url.pathname === '/'} href="/">Главная</a>
					<a class:active={$page.url.pathname === '/stocks'} href="/stocks">Акции</a>
					<a class:active={$page.url.pathname === '/contacts'} href="/contacts">Контакты</a>
				</ul>
			</div>
			<div class="flex items-center lg:pt-2 pt-1 gap-7">
				<a class=" hidden sm:flex font-semibold" href="tel:+79131489035">+7 (913) 148-90-35</a>
				<a
					class="hover:bg-blue-300/40 duration-300 flex items-center justify-center rounded-full sm:w-10 sm:h-10"
					href="tel:+79131489035"
				>
					<Icon icon="bxs:phone-call" color="#33415c" width="28" />
				</a>
				<a
					class="hover:bg-blue-300/40 duration-300 flex items-center justify-center rounded-full sm:w-10 sm:h-10"
					href="https://instagram.com/vremya.uborki.omsk?igshid=YmMyMTA2M2Y=
					"
				>
					<Icon icon="bxl:instagram-alt" color="#33415c" width="28" />
				</a>
				<button
					on:click={decrement}
					class="flex sm:hidden items-center z-20 justify-center rounded-full sm:w-10 sm:h-10"
				>
					<Icon icon="ion:menu" color="#33415c" width="28" />
				</button>
			</div>
		</div>
	</header>
	<slot />
</LocomotiveScrollProvider>

<style>
	.active {
		color: #59aaa4;
	}
	.active2 {
		background-color: #f3f6fb;
	}
</style>
