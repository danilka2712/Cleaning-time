<script>
	import Menu from '../../components/Menu.svelte';
	var map;

	// @ts-ignore
	DG.then(function () {
		// @ts-ignore
		map = DG.map('map', {
			center: [55.018009, 73.35006],
			zoom: 13
		});

		// @ts-ignore
		DG.marker([55.018009, 73.35006]).addTo(map).bindPopup('Омск, Шукшина 11');
	});
</script>

<svelte:head>
	<meta
		name="description"
		content="Время Уборки - Клининговая компания. Омск, Шукшина 11. +7 (913) 148-90-35. Клининговая компания Омская область ВРЕМЯ УБОРКИ. Клининг квартир, домов, офисов. Генеральная уборка. Уборка после ремонта в Омске. "
	/>
	<title>Контакты | Клининг</title>
</svelte:head>
<Menu />

<div  data-scroll-section class=" sm:w-full pt-5 sm:mt-0 bg-white sm:h-screen">
	<div class=" sm:px-32 px-4  flex-col sm:flex sm:w-full">
		<div class="sm:flex justify-between pt-14 items-center">
			<div>
				<h2 class="font-medium text-3xl sm:text-[40px] sm:leading-[2.9rem]">Контакты</h2>
				<div class="pt-4 sm:pt-14">
					<p class="pb-2">Офис</p>
					<h1 class=" font-medium">Омск, Шукшина 11</h1>
				</div>
				<div class="pt-7">
					<p class="pb-2">Телефон</p>
					<h1 class=" font-medium">+7 (913) 148-90-35</h1>
				</div>
				<div class="pt-7">
					<p class="pb-2">Время работы</p>
					<h1 class=" font-medium">Ежедневно с 09:00 до 21:00</h1>
				</div>
			</div>
			<div id="map" class="w-full sm:w-1/2 sm:h-[500px] h-96 mt-20 sm:mt-0" />
		</div>
		<div class="pt-32 flex justify-between" />
	</div>
</div>

<style>
</style>
