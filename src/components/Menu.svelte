<script>
	import { fly } from 'svelte/transition';
	import { expoIn } from 'svelte/easing';

	import { menu } from '../store';
</script>
{#if $menu}
<div
in:fly={{ duration: 500, x: 414, opacity: 100, easing: expoIn }}
out:fly={{ duration: 500, x: -414, opacity: 100, easing: expoIn }}
class=" bg-white fixed top-0 pt-7 w-full z-0 h-screen"
>
<div class="h-[80vh]">
    <div class="flex h-full  items-end">
        <div class="mx-9 flex text-5xl font-light leading-tight flex-col text-[#121212]">
            <a class="text-[#33415c]" href="/">Главная</a>
            <a class="text-[#33415c]" href="/stocks">Акции</a>
            <a class="text-[#33415c]" href="/contacts">Контакты</a>
        </div>
    </div>
</div>
</div>

{/if}
