<script>
	import { infoClean } from '../store';
	import { fade } from 'svelte/transition';
	import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	function decrement2() {
		infoClean.update((x) => (x = false));
	}
</script>

{#if $infoClean}
	<div
		transition:fade={{ delay: 250, duration: 300 }}
		class="w-screen fixed right-0 top-0 z-20 bg-[#33415C]/25 shadow-xl h-screen"
	>
		<div
			transition:slide={{ delay: 250, duration: 500, easing: quintOut }}
			class="w-full  h-full flex justify-center items-center"
		>
			<div class="bg-white mx-4 sm:mx-0 relative rounded-lg lg:w-1/3 p-10">
				<div class="flex flex-col justify-center">
					<h1 class=" text-xl text-center font-medium">Что мы моем</h1>
					<ul class="list-outside list-disc p-5">
						<li class="text-base pb-2 pt-6">Стеклопакеты с 2-х сторон;</li>
						<li class="text-base pb-2">Откосы, рамы, отливы, уплотнители;</li>
						<li class="text-base pb-2">Подоконники;</li>
						<li class="text-base pb-2">Москитные сетки.</li>
					</ul>
					<p class="text-sm">
						*Возможно повышение стоимости:<br /> -при наличии загрязнений после ремонта (краска,
						клей, скотч, пленка, грунтовка и др.) <br />-объект за пределами города; <br />-свыше
						5-го этажа доплата за высоту.
					</p>
					<p class="text-sm">
						*Компания оставляет за собой право повышения стоимости, в случаях не предусмотренных
						прайс листом.
					</p>
					<p class="text-sm">*Все дополнительные услуги рассчитываются индивидуально.</p>
				</div>
				<button on:click={decrement2} class="w-full bg-[#59AAA4] text-white p-2 rounded mt-5">
					ОК
				</button>
			</div>
		</div>
	</div>
{/if}
