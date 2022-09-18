<script lang="ts">
	import Logo1 from '$lib/image/Logo3.svg';
	import { superx } from '../store';
	import { polusex } from '../store';
	import arrow from '$lib/image/arrow.svg';
	import main1 from '$lib/image/main1.jpg';
	import Windows2 from '../components/Windows2.svelte';
	import Windows1 from '../components/Windows1.svelte';
	import Main2 from '../components/Main2.svelte';

	function decrement() {
		superx.update((c) => (c = true));
	}
	function decrement2() {
		polusex.update((x) => (x = true));
	}

	const rewars = [
		{
			id: 1,
			name: 'Алексей',
			text: 'Отмыли квартиру сверху донизу, все чисто и блестит. Уборка проведена великолепно, отмыли даже въевшуюся грязь на кухонном гарнитуре. Всем доволен, спасибо за работу.'
		},
		{
			id: 2,
			name: 'Татьяна',
			text: 'Заказывали уборку после ремонта, остались очень довольны компанией. Специалисты справились на ура, все вычистили, помыли, навели красоту. Будем обращаться сюда!'
		},
		{
			id: 3,
			name: 'Борис',
			text: 'Молодцы. Профессионалы, свой инструмент, химия. Работают слаженно, на крупные заказы приезжают несколько мастеров. По времени пунктуальны. Рекомендую👍🏻'
		},
		{
			id: 4,
			name: 'Ксения',
			text: 'Не пожалели, что обратились именно сюда. Заказывали генеральную уборку. Уборку провели на отлично! Придраться просто не к чему. За адекватную цену – качественная услуга!'
		}
	];
	const items = [
		{
			id: 1,
			name: 'Поддерживающая',
			text: 'Вернем жилищу уют и сияющую чистоту. ',
			price: '1800₽ '
		},
		{
			id: 2,
			name: 'Генеральная',
			text: 'Чистота может быть идеальной',
			price: '170-200₽  м<sup>2</sup>'
		},
		{
			id: 3,
			name: 'После ремонта',
			text: 'Уберем всю пыль и грязь после ремонта',
			price: '350-400₽  м<sup>2</sup>'
		},
		{
			id: 4,
			name: 'Мытье окон',
			text: 'Смотрите на мир через чистые окна!',
			price: '250₽  м<sup>2</sup>'
		}
	];
</script>

<Windows2 />
<Windows1 />

<div
	data-scroll-section
	class="bg-white"
>
	<div class="sm:mx-32 mx-4  sm:pt-14 sm:flex items-center sm:pb-32 justify-between">
		<div class="">
			<h1 class="sm:text-5xl pt-20 sm:pt-0 sm:mt-0 text-3xl font-medium">
				Профессиональные <br />клининговые <br /> услуги в Омске
			</h1>
			<p class="sm:mt-12 mt-4 sm:text-lg">
				Стабильно высокое качество уборок <br /> для частных лиц и бизнеса на лучших условиях
				<br /><span class="sm:flex hidden">в СНГ с гарантией по договору</span>
			</p>
		</div>
		<div>
			<img class=" sm:mt-0 mt-6" src={main1} alt="" />
		</div>
	</div>
</div>

<main class="">
	<div data-scroll-section class="sm:h-screen sm:mt-0 mt-20  bg-[#F3F6FB]">
		<div class="sm:flex sm:mx-32 mx-4 pt-16 pb-8   sm:py-24   justify-between">
			<div>
				<h2 class="font-medium text-3xl sm:text-[40px] sm:leading-[2.9rem]">
					У нас понятные<br />и прозрачные цены<br />на клининг
				</h2>
			</div>
			<div>
				<p class="text-lg mt-4 sm:mt-0">
					Мы за честные цены. Клиенты нашей<br />компании также могут сэкономить<br />оформив
					подписку на уборку.
				</p>
			</div>
		</div>
		<div class="flex flex-col sm:flex-row sm:mx-32 mx-4 gap-5 sm:gap-8 justify-between ">
			{#each items as i}
				<div class="bg-white rounded-lg w-full p-7">
					<div>
						<h1 class=" text-xl sm:text-lg font-medium pb-4">{i.name}</h1>
						<p class="text-lg sm:text-base">{i.text}</p>
					</div>
					<div class="flex sm:mt-14 mt-8 items-end">
						<h1 class="text-xl font-medium sm:text-lg">от {@html i.price}</h1>
					</div>
				</div>
			{/each}
		</div>
	</div>
	<Main2 />
	<div data-scroll-section class="sm:h-screen bg-[#F3F6FB] sm:flex sm:gap-32 ">
		<div class="sm:mx-32 mx-4 sm:w-full pt-16 pb-8 sm:py-0  sm:items-center sm:flex">
			<div class="sm:w-1/2">
				<h2 class="font-medium text-3xl sm:text-[40px] sm:leading-[2.9rem]">
					Лучшие клиенты — <br />
					наши клиенты!
				</h2>
				<p class="text-lg font-normal pt-5">
					Оставить пожалуйста ваш отзыв<br />
					благодаря ему мы будем знать как <br />
					улучшить наш сервис
				</p>
				<div class="sm:flex  pb-14 sm:pb-0  pt-7 gap-3 items-center">
					<p class="text hidden sm:flex  font-semibold uppercase text-[#59AAA4]">Оставить отзыв</p>
					<button
						on:click={decrement}
						class="p-4 px-4 hidden hover:scale-125 duration-300 sm:flex items-center justify-center rounded-full bg-[#59AAA4]"
					>
						<img width="24" class="" src={arrow} alt="" />
					</button>
					<button on:click={decrement}
						class="bg-[#59AAA4] sm:hidden font-medium w-full text-white p-3 rounded-lg text-lg"
						>Оставить отзыв</button
					>
				</div>
			</div>
			<div class="sm:w-1/2">
				<div class="sm:grid sm:grid-cols-2 flex flex-col gap-7">
					{#each rewars as r}
						<div class=" bg-white p-7">
							<h1 class=" text-xl font-semibold">{r.name}</h1>
							<p class="text-base pt-4">{r.text}</p>
							<p class="text-[#59AAA4] pt-4 font-medium">Все отзывы...</p>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</div>
	<div data-scroll-section class="sm:h-[80vh] py-14 sm:py-0  bg-[#F3F6FB] ">
		<div class="sm:mx-32  pb-8 sm:py-0  mx-4 sm:pt-36">
			<div class=" sm:flex sm:justify-between sm:items-end">
				<div>
					<h2 class="font-medium text-3xl sm:text-[40px] sm:leading-[2.9rem]">Возникли вопросы?</h2>
				</div>
				<div>
					<p class="text-lg font-normal pt-5">
						Позвоните по номеру 20-90-35 или оставьте свои контакты <br /> наши менеджеры свяжутся с
						вами в ближайшее время!
					</p>
				</div>
			</div>
			<div class="pt-12">
				<form class="flex flex-col sm:flex-row rounded-lg  bg-white sm:p-14 p-8 gap-5" action="">
					<input
						placeholder="Ваше имя"
						class="w-full rounded-lg  h-14 p-4 border-[#5C677D]/50 border"
						type="text"
					/>
					<input
						placeholder="Номер телефона"
						class="w-full rounded-lg  h-14 p-4 border-[#5C677D]/50 border"
						type="text"
					/>
					<input
						placeholder="Укажите нужную вам услугу"
						class="w-full rounded-lg  h-14 p-4 border-[#5C677D]/50 border"
						type="text"
					/>
					<button class="bg-[#59AAA4] rounded-lg  text-lg text-white p-4 w-full "
						>Оставить заявку</button
					>
				</form>
			</div>
		</div>
	</div>
</main>

<div class="bg-[#59AAA4] sm:h-[35vh] flex" data-scroll-section>
	<div class="sm:mx-32 w-full mx-4 pt-16">
		<div class="flex justify-between items-center sm:items-start">
			<div>
				<img class="w-48 sm:w-52" src={Logo1} alt="" />
			</div>
			<div class="text-white">
				<p class="text-[#F3F6FB] sm:text-lg">Контакты</p>
				<p class="text-[#F3F6FB] sm:text-lg">+7(913)148-90-35</p>
				<p class="text-[#F3F6FB] sm:text-lg">20-90-35</p>
			</div>
		</div>
	</div>
</div>

<style>
</style>
