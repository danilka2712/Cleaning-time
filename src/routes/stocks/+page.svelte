<script>
	import Act1 from '../../lib/image/Act1.svg';
	import Act2 from '../../lib/image/Act2.svg';
	import Menu from '../../components/Menu.svelte';

	import axios from 'axios';
	import { polusex } from '../../store';
	import { imask } from '@imask/svelte';
	import Windows1 from '../../components/Windows1.svelte';
	let number = '';
	let name = '';

	function decrement() {
		polusex.update((c) => (c = true));
	}

	const options = {
		mask: '+{7}(000)000-00-00',
		lazy: true
	};

	function accept({ detail: imask }) {
		console.log('accepted', imask);
	}

	function complete({ detail: imask }) {
		console.log('completed', imask);
	}

	const token = '6114170119:AAHBQ6vEnQ-PKJvws0ARcGRg9Ysypk5_aSo';
	const chatId = 5631311370;
	function submit() {
		const fullMessage = `Новая заявка%0AНомер телефона: ${number}%0AИмя: ${name}`;
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
	<meta
		name="description"
		content="Безупречный клининг — хорошо, а дополнительные скидки и подарки ещё лучше! Скидка за репост! Скидка на первый заказ!"
	/>
	<title>Акции | Клининг</title>
</svelte:head>
<Menu />
<Windows1 />

<div data-scroll-section class="box sm:w-full sm:mt-0 pt-5 px-4 sm:px-0 sm:h-screen">
	<div class="sm:py-16 sm:px-32 sm:flex sm:w-full sm:items-center">
		<div class="sm:w-1/2 pt-14">
			<div>
				<h2 class="font-medium text-3xl sm:text-[40px] sm:leading-[2.9rem]">
					Ни дня без скидок<br />
				</h2>
				<p class="mt-2">Выгодные цены, скидки и интересные предложения.</p>
			</div>
			<form
				on:submit|preventDefault={submit}
				class="bg-white hidden sm:flex mt-12 shadow-sm flex-col sm:flex-row gap-5 sm:mt-14 p-8 rounded"
			>
				<input
					bind:value={name}
					placeholder="Ваше имя"
					class="p-3 border-[#5C677D]/50 w-full border rounded"
					type="text"
					name=""
					id=""
				/>
				<input
					required
					use:imask={options}
					on:accept={accept}
					on:complete={complete}
					bind:value={number}
					placeholder="Номер телефона"
					class="p-3 w-full border border-[#5C677D]/50 rounded"
					type="tel"
				/>
				<button on:click={decrement} class="p-3 w-full text-white bg-[#59AAA4] rounded"
					>Отправить</button
				>
			</form>
		</div>
		<div class="sm:w-1/2 mt-12 sm:mt-0">
			<div class="flex flex-col gap-5 sm:gap-9 items-end">
				<img class="sm:w-3/4 shadow-sm" src={Act1} alt="" />
				<img class="sm:w-3/4 shadow-sm" src={Act2} alt="" />
			</div>
			<form
				on:submit|preventDefault={submit}
				class="bg-white flex sm:hidden mt-12 shadow-sm flex-col sm:flex-row gap-5 sm:mt-14 p-8 rounded"
			>
				<input
					bind:value={name}
					placeholder="Ваше имя"
					class="p-3 border-[#5c677d] w-full border rounded"
					type="text"
					name=""
					id=""
				/>
				<input
					use:imask={options}
					on:accept={accept}
					on:complete={complete}
					bind:value={number}
					placeholder="Номер телефона"
					class="p-3 w-full border border-[#5c677d] rounded"
					type="tel"
				/>
				<button on:click={decrement} class="p-3 w-full text-white bg-[#59AAA4] rounded"
					>Отправить</button
				>
			</form>
		</div>
	</div>
</div>

<style>
	.box {
		background-color: hsl(217, 50%, 97%);
	}
	input::placeholder {
		color: #5c677d;
	}
</style>
