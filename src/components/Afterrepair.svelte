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
<div transition:fade={{ delay: 250, duration: 300 }} class="w-screen fixed right-0 top-0 z-20 bg-[#33415C]/25 shadow-xl h-screen">
	<div transition:slide={{ delay: 250, duration: 500, easing: quintOut }} class="w-full h-full flex justify-center items-center">
			<div class="bg-white mx-4 sm:mx-0 relative rounded-lg lg:w-1/3 p-10">
				<div class="flex flex-col justify-center">
					<h1 class=" text-xl text-center font-medium">Что входит в уборку</h1>
					<ul class="list-outside list-disc p-5">
						<li class="text-base pb-2 pt-6">Обеспыливание поверхностей;</li>
						<li class="text-base pb-2">Удаление строительных загрязнений;</li>
						<li class="text-base pb-2">Мытье стен, потолка, пола, плинтусов;</li>
						<li class="text-base pb-2">Мытье окон внутри;</li>
						<li class="text-base pb-2">Мытье осветительных приборов;</li>
						<li class="text-base pb-2">Мытье всех фасадов мебели;</li>
						<li class="text-base pb-2">Очищение радиаторов и батарей;</li>
						<li class="text-base pb-2">Очищение дверей, дверных проемов;</li>
						<li class="text-base pb-2">Обеспыливание мебели снаружи и внутри;</li>
					</ul>
					<p class="text-sm">
						*Компания оставляет за собой право повышения стоимости, в случаях не предусмотренных
						прайс листом
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
