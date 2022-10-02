<script>
	import { infoClean } from '../store.js';
	import Icon from '@iconify/svelte';
	function decrement() {
		infoClean.update((x) => (x = false));
	}
	import { slide,fade } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
</script>

{#if $infoClean}
	<div transition:fade="{{delay: 250, duration: 300}}" class="w-screen  right-0  fixed top-0 z-20 bg-[#33415C]/30 shadow-xl h-screen">
		<div
			transition:slide={{ delay: 250, duration: 300, easing: quintOut }}
			class="w-full h-full flex justify-center items-center"
		>
			<div
				class="flex sm:mx-0 mx-4 bg-white rounded-lg lg:p-16 p-5 sm:py-0 py-10 flex-col "
			>
				<div class="flex  justify-between items-center">
					<h2 class="font-medium flex text-2xl lg:text-[35px] lg:leading-[2.9rem]">Что мы моем?</h2>
					<button on:click={decrement} class="sm:mt-2"
						><Icon width="24" icon="codicon:chrome-close" color="#33415c" /></button
					>
				</div>

				<ul class="list-outside py-5">
					<li class="text-base pb-2 pt-6">– Стеклопакеты с 2-х сторон</li>
					<li class="text-base pb-2">– Откосы, рамы, отливы, уплотнители</li>
					<li class="text-base pb-2">– Подоконники</li>
					<li class="text-base pb-2">– Москитные сетки.</li>
				</ul>
				<p class="text-sm">
					*Возможно повышение стоимости:<br /> -при наличии загрязнений после ремонта <br />(краска,
					клей, скотч, пленка, грунтовка и др.) <br />-объект за пределами города; <br />-свыше 5-го
					этажа доплата за высоту.
				</p>
				<p class="text-sm">
					*Компания оставляет за собой право повышения стоимости, в случаях не предусмотренных прайс
					листом.
				</p>
				<p class="text-sm">*Все дополнительные услуги рассчитываются индивидуально.</p>
			</div>
		</div>
	</div>
{/if}
