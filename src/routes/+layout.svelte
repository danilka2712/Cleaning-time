<script>
  import LocomotiveScrollProvider from 'svelte-locomotive-scroll';
	import 'locomotive-scroll/src/locomotive-scroll.scss';
	import Logo from '$lib/image/Logo2.svg';
	import Phone from '$lib/image/Phone.svg';
	import Vk from '$lib/image/Vk.svg';
	import { page } from '$app/stores';

	console.log()
	import '../app.css';
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
<header data-scroll-section  class:active2={$page.url.pathname === '/stocks'} class="bg-white">
	<div class="sm:mx-32  mx-4 pt-5 flex justify-between sm:items-center">
		<div>
			<img class="w-48 sm:w-52" src={Logo} alt="" />
		</div>
		<div>
			<ul class="sm:flex hidden gap-8 font-medium">
				<a class:active={$page.url.pathname === '/'} href="/">Главная</a>
				<a class:active={$page.url.pathname === '/stocks'} href="/stocks">Акции</a>
				<a class:active={$page.url.pathname === '/contacts'} href="/contacts">Контакты</a>
			</ul>
			
		</div>
		<div class="flex items-center gap-7">
			<a class=" hidden sm:flex font-semibold" href="tel:+20-48-72">20-90-35</a>
			<a class="hover:bg-blue-300/40 duration-300 flex items-center justify-center rounded-full sm:w-10 sm:h-10" href="tel:+20-48-72">
			<img class="w-5 box" src={Phone} alt="" />
	
			</a>
			<a class="hover:bg-blue-300/40 duration-300 flex items-center justify-center rounded-full sm:w-10 sm:h-10" href="https://vk.com/">
				<img class="w-7" src={Vk} alt="" />
		
				</a>
		</div>
	</div>
</header>
	<slot />
</LocomotiveScrollProvider>

<style>
 .active {
	color:#59AAA4;
 }	
 .active2{
	background-color: #f3f6fb;

 }
</style>