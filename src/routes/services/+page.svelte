<script>
    	import service from '../../lib/image/Service.jpg';
		import Menu from '../../components/Menu.svelte';

	const items = [
		{ id: 1, text: 'Генеральная уборка', price: '170-200' },
		{ id: 2, text: 'Поддерживающая', price: '1800' },
		{ id: 3, text: 'Послестроительная', price: '350-400' },
		{ id: 4, text: 'Уборка кухни под ключ', price: '500' },
		{ id: 5, text: 'Уборка санузла', price: '150-250' },
		{ id: 6, text: 'Мытье окон', price: '250' }
	];
    const DopItems = [
		{ id: 1, text: 'Глажка одежды', price: '600р/час' },
		{ id: 2, text: 'Штора (глажка/стирка)', price: '200р погон.метр' },
		{ id: 3, text: 'Очищение обуви', price: '150р/пара' },
		{ id: 4, text: 'Смена постельного белья', price: '250-300р' },
		{ id: 5, text: 'Духовой шкаф внутри', price: '800-1500р' },
		{ id: 6, text: 'Холодильник внутри', price: 'от 500р' },
		{ id: 6, text: 'Микроволновая печь внутри', price: 'от 300р' },

	];
</script>

<svelte:head>
	<meta
		name="description"
		content="Безупречный клининг — хорошо, а дополнительные скидки и подарки ещё лучше! Скидка за репост! Скидка на первый заказ!"
	/>
	<title>Услуги | Клининг</title>
</svelte:head>
<Menu/>

<div data-scroll-section class="sm:w-full bg-white sm:mt-0 mt-14 px-4 sm:px-0 sm:h-screen">
	<div class="sm:py-16 sm:px-32 sm:flex lg:items-center sm:w-full ">
		<div class="sm:w-1/2">
			<div>
				<h2 class="font-medium text-2xl sm:text-[40px] sm:leading-[2.9rem]">Все услуги</h2>
			</div>
			<div class="w-full mt-8">
				{#each items as i}
					<div class="flex gap-12">
						<p class="w-1/2 text-sm sm:text-base">{i.text}</p>
						<p class="text-sm sm:text-base">от {i.price}р m<sup>2</sup></p>
					</div>
				{/each}
			</div>
            <div class="w-full mt-14">
                <h1 class="mb-4 text-lg lg:text-xl">Дополнительные услуги</h1>
				{#each DopItems as i}
					<div class="flex gap-12">
						<p class="w-1/2 text-sm sm:text-base">{i.text}</p>
						<p class="text-sm sm:text-base">{i.price}</p>
					</div>
				{/each}
			</div>
            <div class="mt-10">
                <p class="text-sm">
					*Компания оставляет за собой право повышения стоимости, в случаях не предусмотренных прайс
					листом
				</p>
            </div>
		</div>
		<div class="sm:w-1/2  mt-12 sm:mt-0">
            <img class=" z-0" src={service} alt="">
        </div>
	</div>
</div>

<style>
</style>
