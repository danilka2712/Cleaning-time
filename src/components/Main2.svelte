<script>
	import main2 from '$lib/image/main2.jpg';
	import Icon from '@iconify/svelte';
	import arrow from '$lib/image/arrow.svg';
	import axios from 'axios';
	import { superx } from '../store';

	function decrement() {
		superx.update((c) => (c = true));
	}
	let options = 'Телефон';

	const metr = [
		{ id: 1, metr: '40' },
		{ id: 1, metr: '45' },
		{ id: 1, metr: '55' },
		{ id: 1, metr: '65' },
		{ id: 1, metr: '75+' }
	];
	const metrMob = [
		{ id: 1, metr: '40' },
		{ id: 1, metr: '50' },
		{ id: 1, metr: '60' },
		{ id: 1, metr: '70+' }
	];

	let metrow = '40';
	let menu = ['Комплексная', 'Генеральная', 'Несколько комнат', 'Быстрая уборка'];
	let flavours = ['Комплексная'];
	let number = '+7';
	const token = '5312487588:AAHrH9cNC5-amKNacngShd3ljnOwaJOmsHs';
	const chatId = 596613157;
	function submit() {
		const fullMessage = `Расчет стоимости%0AНомер телефона: ${number}%0AКвадратных метров: ${metrow}%0AУслуга: ${flavours}%0AСпособ связи: ${options}`;
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
	}
</script>

<div data-scroll-section class="sm:h-screen bg-[#F3F6FB]  ">
	<div
		class="flex-col-reverse sm:gap-32 sm:items-center flex pt-24 pb-8 sm:py-0 sm:flex-row sm:mx-0 mx-4 "
	>
		<div>
			<img class="sm:h-screen sm:w-[49.5vw] " src={main2} alt="" />
		</div>
		<div>
			<h2 class="font-medium text-3xl sm:text-[40px] sm:leading-[2.9rem]">
				Мы работаем<br />вы отдыхаете
			</h2>
			<div class="flex mt-5 flex-col">
				<form on:submit|preventDefault={submit} class="">
					<p class=" text-sm">Общая площадь</p>
					<div class="mt-3 sm:flex hidden gap-5 flex">
						{#each metr as m}
							<div
								on:click={() => (metrow = m.metr)}
								class:active={metrow === m.metr}
								class=" bg-white rounded cursor-pointer p-3 px-4"
							>
								<p class:activeText={metrow === m.metr}>{m.metr}m<sup>2</sup></p>
							</div>
						{/each}
					</div>
					<div class="mt-3 sm:hidden gap-5 flex">
						{#each metrMob as m}
							<div
								on:click={() => (metrow = m.metr)}
								class:active={metrow === m.metr}
								class=" bg-white rounded cursor-pointer p-3 px-4"
							>
								<p class:activeText={metrow === m.metr}>{m.metr}m<sup>2</sup></p>
							</div>
						{/each}
					</div>
					<div class="mt-10 mb-3">
						<p class=" text-sm">Выберите услугу</p>
					</div>
					<div class="grid grid-cols-2 gap-2">
						{#each menu as m}
							<div class="form-check">
								<input
									bind:group={flavours}
									class="form-check-input appearance-none h-4 w-4 border border-gray-300 rounded-sm bg-white checked:bg-[#59AAA4] checked:border-[#59AAA4] focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2 cursor-pointer"
									type="checkbox"
									value={m}
								/>
								<label class="form-check-label inline-block text-gray-800" for={m}>
									{m}
								</label>
							</div>
						{/each}
					</div>
					<div class="mt-7">
						<p class="pb-3 text-sm">Ваш номер телефона</p>
						<div class="flex">
							<input
								bind:value={number}
								placeholder="Номер телефона"
								class="p-3 w-56 rounded"
								type="tel"
								maxlength="12"
							/>
							<div
								class:activeOption={options === 'Телефон'}
								on:click={() => (options = 'Телефон')}
								class="p-3 px-4 ml-4 border-2 border-[#5c677d] rounded flex items-center justify-center"
							>
								<Icon icon="carbon:phone-voice-filled" />
							</div>
							<div
								class:activeOption={options === 'Телеграм'}
								on:click={() => (options = 'Телеграм')}
								class="p-3 px-4 ml-4 border-2 border-[#5c677d] rounded flex items-center justify-center"
							>
								<Icon icon="file-icons:telegram" />
							</div>
						</div>
					</div>
					<div class="flex pb-14 sm:pb-0 pt-7 gap-3 items-center">
						<p class="text hidden sm:flex font-semibold uppercase text-[#59AAA4]">
							Рассчитать стоимость
						</p>
						<button
							on:click={decrement}
							class="p-4 px-4 hidden  hover:scale-125 duration-300 sm:flex items-center justify-center rounded-full bg-[#59AAA4]"
						>
							<img width="24" class="" src={arrow} alt="" />
						</button>
						<button
							class="bg-[#59AAA4] sm:hidden font-medium w-full text-white p-3 rounded-lg text-lg"
							>Рассчитать стоимость</button
						>
					</div>
				</form>
			</div>
		</div>
	</div>
</div>

<style>
	.active {
		background-color: #59aaa4;
	}
	.activeText {
		color: #ffffff;
	}
	.activeOption {
		background-color: #5c677d;
		color: #ffffff;
	}
</style>
