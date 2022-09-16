<script>
import { polusex } from '../store';

function decrement2() {
		polusex.update(x => x = false);
	}
	

</script>

{#if $polusex}
<div class="w-screen absolute right-0 top-0 z-20 bg-[#33415C]/30 shadow-xl h-screen">
	<div class="w-full h-full flex justify-center items-center">
		<div class="bg-white relative rounded-lg w-72 p-10">
            
			<div class="flex flex-col justify-center">
				<h1 class="text-center text-xl font-medium">Отправлено</h1>
				<p class="text-center my-3">Спасибо что выбрали нас, мы скоро с вами свяжимся</p>
			</div>
			<button on:click={decrement2} class="w-full bg-[#59AAA4] text-white p-2 rounded mt-5">
				ОК
            </button>
		</div>
	</div>
</div>

{/if}
