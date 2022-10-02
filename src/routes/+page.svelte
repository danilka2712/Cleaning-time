<script lang="ts">
	import Logo1 from '$lib/image/Logo5.svg';
	import Icon from '@iconify/svelte';
	import { superx, infoClean } from '../store';

	import Phone from '$lib/image/Phone.svg';
	import Vk from '$lib/image/Vk.svg';
	import arrow from '$lib/image/arrow.svg';
	import main1 from '$lib/image/main1.jpg';
	import Windows2 from '../components/Windows2.svelte';
	import Windows1 from '../components/Windows1.svelte';

	import Main2 from '../components/Main2.svelte';
	import Usluga1 from '../components/usluga1.svelte';
	import Usluga2 from '../components/usluga2.svelte';
	import Usluga3 from '../components/usluga3.svelte';
	import Usluga4 from '../components/usluga4.svelte';

	function decrement() {
		superx.update((c) => (c = true));
	}
	function decrement2() {
		infoClean.update((c) => (c = true));
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
			price: '1800₽ ',
			link: '/supporting'
		},
		{
			id: 2,
			name: 'Генеральная',
			text: 'Чистота может быть идеальной',
			price: '170-200₽  м<sup>2</sup>',
			link: '/general'
		},
		{
			id: 3,
			name: 'После ремонта',
			text: 'Уберем всю пыль и грязь после ремонта',
			price: '350-400₽  м<sup>2</sup>',
			link: '/afterrepair'
		},
		{
			id: 4,
			name: 'Мытье окон',
			text: 'Смотрите на мир через чистые окна!',
			price: '250₽  м<sup>2</sup>',
			link: '/washwin'
		}
	];
	import { polusex } from '../store';

	let textSet = 'Поддерживающая';
	let name = '';
	let number = '';
	let service = '';
	import axios from 'axios';

	const token = '5312487588:AAHrH9cNC5-amKNacngShd3ljnOwaJOmsHs';
	const chatId = 596613157;
	function submit() {
		const fullMessage = `Расчет стоимости%0AИмя: ${name}%0AНомер телефона: ${number}%0AВид услуги: ${service}`;
		axios
			.post(
				`https://api.telegram.org/bot${token}/sendMessage?chat_id=${chatId}&text=${fullMessage}`
			)
			.then(
				(response) => {
					console.log('SUBMIT', response);
				},
				(error) => {
					console.log(error);
				}
			);
		polusex.update((c) => (c = true));
	}

</script>
<svelte:head>
	<meta name="description" content="Клининговая компания ВРЕМЯ УБОРКИ – профессиональные клининг услуги в Омской области. Только надежные клинеры и качественная химия. ">
	<title>Клининг | Омск</title>
</svelte:head>
<Windows2 />
<Windows1 />
{#if textSet === 'Поддерживающая'}
	<Usluga1 />
{:else if textSet === 'Генеральная'}
	<Usluga2 />
{:else if textSet === 'После ремонта'}
	<Usluga3 />
{:else if textSet === 'Мытье окон'}
	<Usluga4 />
{/if}
<div data-scroll-section class="bg-white">
	<div
		class="xl:mx-32 lg:mx-10 sm:mx-14 mx-4 gap-10  sm:pt-14 sm:flex items-center sm:pb-32 justify-between"
	>
		<div class="">
			<h1 class="lg:text-5xl pt-20 sm:pt-0 sm:mt-0 text-3xl font-medium">
				Профессиональные <br />клининговые <br /> услуги в Омске
			</h1>
			<p class="sm:mt-12 mt-4 lg:text-lg">
				Стабильно высокое качество уборок <br /> для частных лиц и бизнеса на лучших условиях
				<br class="sm:hidden lg:flex" /><span class="lg:flex hidden"
					>в СНГ с гарантией по договору</span
				>
			</p>
		</div>
		<div>
			<img class=" sm:mt-0 mt-6" src={main1} alt="" />
		</div>
	</div>
</div>

<main class="">
	<div data-scroll-section class="lg:h-screen sm:mt-0 mt-20 bg-[#F3F6FB]">
		<div class="sm:flex xl:mx-32 lg:mx-10 sm:mx-14 mx-4 pt-16 pb-8   sm:py-24   justify-between">
			<div>
				<h2 class="font-medium  sm:text-2xl text-3xl lg:text-[40px] lg:leading-[2.9rem]">
					У нас понятные<br />и прозрачные цены<br />на клининг
				</h2>
			</div>
			<div>
				<p class="lg:text-lg mt-4 sm:mt-0">
					Мы за честные цены. Клиенты нашей<br />компании также могут сэкономить<br />оформив
					подписку на уборку.
				</p>
			</div>
		</div>
		<div
			class=" grid lg:grid-cols-4 sm:grid-cols-2 xl:mx-32 lg:mx-10 sm:mx-14 mx-4 gap-5 sm:gap-8 justify-between "
		>
			{#each items as i}
				<div class="bg-white rounded-lg w-full p-7">
					<div>
						<h1 class=" text-xl sm:text-lg font-medium pb-4">{i.name}</h1>
						<p class="text-lg sm:text-base">{i.text}</p>
					</div>
					<div class="flex sm:mt-14 mt-8 item-center  justify-between ">
						<h1 class="text-xl font-medium sm:text-lg">от {@html i.price}</h1>
						<button on:click={decrement2} on:click={() => (textSet = i.name)}>
							<Icon width="22" color="#33415c" hight="22" icon="codicon:info" />
						</button>
					</div>
				</div>
			{/each}
				<a sveltekit:reload class="flex mt-4 lg:col-span-4 text-[#5c677d] sm:col-span-4 justify-end items-center gap-2 " href="/services">Все услуги<Icon icon="bi:arrow-right" color="#5c677d" /></a>


		</div>
	</div>

	<Main2 />
	<div data-scroll-section class="lg:h-screen bg-[#F3F6FB] lg:flex sm:gap-32 ">
		<div
			class="xl:mx-32 lg:mx-10 sm:mx-14 mx-4 lg:w-full pt-16 pb-8 sm:py-0  sm:items-center lg:flex"
		>
			<div class="lg:w-1/2">
				<h2 class="font-medium  sm:text-2xl text-3xl lg:text-[40px] lg:leading-[2.9rem]">
					Лучшие клиенты — <br />
					наши клиенты!
				</h2>
				<p class="lg:text-lg mt-4 sm:mt-4 mt-4">
					Оставьте пожалуйста ваш отзыв<br />
					благодаря ему мы будем знать как <br />
					улучшить наш сервис
				</p>
				<div class="sm:flex  pb-14 sm:pb-0 sm:mb-10 lg:mb-0  pt-7 gap-3 items-center">
					<p class="lg:text-base text-sm hidden sm:flex font-semibold uppercase text-[#59AAA4]">
						Оставить отзыв
					</p>
					<button
						on:click={decrement}
						class="lg:p-4 lg:px-4 px-2 p-2 hidden  hover:scale-125 duration-300 sm:flex items-center justify-center rounded-full bg-[#59AAA4]"
					>
						<img width="24" class="" src={arrow} alt="" />
					</button>
					<button
						on:click={decrement}
						class="bg-[#59AAA4] sm:hidden font-medium w-full text-white p-3 rounded-lg text-lg"
						>Оставить отзыв</button
					>
				</div>
			</div>
			<div class="lg:w-1/2">
				<div class="sm:grid sm:grid-cols-2 flex flex-col gap-7">
					{#each rewars as r}
						<div class=" bg-white p-7">
							<h1 class=" lg:text-xl text-base font-semibold">{r.name}</h1>
							<p class="lg:text-base text-sm pt-4">{r.text}</p>
							<p class="text-[#59AAA4] pt-4 text-sm lg:text-base lg:font-medium">Все отзывы...</p>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</div>
	<div data-scroll-section class="sm:h-[80vh] lg:py-14 sm:py-0  bg-[#F3F6FB] ">
		<div class="xl:mx-32 lg:mx-10  pb-8 sm:py-0  mx-4 sm:pt-36">
			<div class=" sm:flex sm:justify-between sm:items-end">
				<div>
					<h2 class="font-medium  sm:text-2xl text-3xl lg:text-[40px] lg:leading-[2.9rem]">
						Возникли вопросы?
					</h2>
				</div>
				<div>
					<p class="lg:text-lg mt-4 sm:mt-4 mt-4">
						Позвоните по номеру 20-90-35 или оставьте свои контакты <br class="hidden lg:flex" /> наши
						менеджеры свяжутся с вами в ближайшее время!
					</p>
				</div>
			</div>
			<div class="pt-12">
				<form
					on:submit|preventDefault={submit}
					class="flex flex-col sm:flex-row rounded-lg  bg-white lg:p-14 p-8 gap-5"
					action=""
				>
					<input
						bind:value={name}
						placeholder="Ваше имя"
						minlength="3"
						class="w-full hidden capitalize lg:flex rounded-lg  h-14 p-4 border-[#5C677D]/50 border"
						type="text"
					/>
					<input
						bind:value={number}
						required
						maxlength="12"
						minlength="11"
						placeholder="Номер телефона"
						class="w-full rounded-lg  h-14 p-4 border-[#5C677D]/50 border"
						type="text"
					/>
					<input
						bind:value={service}
						placeholder="Укажите услугу"
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

<div class="bg-[#59AAA4]  flex" data-scroll-section>
	<div class="xl:mx-32 lg:mx-10 w-full mx-4 py-16">
		<div class="flex justify-between items-center">
			<div>
				<img class="w-48 sm:w-52" src={Logo1} alt="" />
			</div>
			<div class="flex items-center gap-7 sm:pt-3">
				<a class=" hidden text-white lg:flex font-semibold" href="tel:+79131489035"
					>+7 (913) 148-90-35</a
				>
				<a
					class="hover:bg-blue-300/40 duration-300 flex items-center justify-center rounded-full sm:w-10 sm:h-10"
					href="tel:+79131489035"
				>
					<img class="w-5 filter-white" src={Phone} alt="" />
				</a>
				<a
					class="hover:bg-blue-300/40 duration-300 flex items-center justify-center rounded-full sm:w-10 sm:h-10"
					href="https://vk.com/"
				>
					<img class="w-7 filter-white" src={Vk} alt="" />
				</a>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	.filter-white {
		filter: invert(100%) sepia(100%) saturate(100%) hue-rotate(86deg) brightness(228%)
			contrast(119%);
	}
</style>
