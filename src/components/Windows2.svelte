<script>
	import axios from 'axios';

    import Close from '../lib/image/close-big.svg'
import { superx } from '../store';
function closeWindow(){
	superx.update(c => c = false);
}
let name = ''
let email = ''
let text = ''
const token = '5312487588:AAHrH9cNC5-amKNacngShd3ljnOwaJOmsHs';
	const chatId = 596613157;
	function submit() {
		const fullMessage = `ОТЗЫВ%0AИмя: ${name}%0AEmail: ${email}%0AОтзыв: ${text}`;
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
			superx.update(c => c = false);
	}
</script>

{#if $superx}
<div class="w-screen fixed top-0 z-20 bg-[#33415C]/30 shadow-xl h-screen">
	<div class="w-full h-full flex justify-center items-center">
		<div class="bg-white relative rounded-lg w-96  p-10">
            <button on:click={closeWindow} class=" absolute top-5 right-10">
                <img width="24" class="" src={Close} alt="">
            </button>
			<form on:submit|preventDefault={submit} action="" class="flex flex-col gap-7">
				<h1 class=" font-medium text-xl text-center">Оставить отзыв</h1>
				<input bind:value={name} placeholder="Ваше имя" class="border-[#5C677D]/50 border rounded-lg p-3" type="text" />
				<input bind:value={email} placeholder="Почта" class="border-[#5C677D]/50 border rounded-lg p-3" type="text" />
                <textarea placeholder="Ваш отзыв" bind:value={text} class="border-[#5C677D]/50 border rounded-lg p-3" name="" id="" cols="4" rows="3"></textarea>
				<button class=" bg-[#59AAA4] p-3 rounded-lg text-white">Отправить</button>
			</form>
		</div>
	</div>
</div>

{/if}
