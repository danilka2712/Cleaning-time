<script>
    import Close from '../lib/image/close-big.svg'
import { superx } from '../store';

function decrement() {
		superx.update(c => c = false);
	}

</script>

{#if $superx}
<div class="w-screen absolute z-20 bg-[#33415C]/30 shadow-xl h-screen">
	<div class="w-full h-full flex justify-center items-center">
		<div class="bg-white relative rounded-lg w-96  p-10">
            <button on:click={decrement} class=" absolute top-5 right-10">
                <img width="24" class="" src={Close} alt="">
            </button>
			<form action="" class="flex flex-col gap-7">
				<h1 class=" font-medium text-xl text-center">Оставить отзыв</h1>
				<input placeholder="Ваше имя" class="border-[#5C677D]/50 border rounded-lg p-3" type="text" />
				<input placeholder="Почта" class="border-[#5C677D]/50 border rounded-lg p-3" type="text" />
                <textarea class="border-[#5C677D]/50 border rounded-lg p-3" name="" id="" cols="4" rows="3"></textarea>
				<button class=" bg-[#59AAA4] p-3 rounded-lg text-white">Отправить</button>
			</form>
		</div>
	</div>
</div>

{/if}
