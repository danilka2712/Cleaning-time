
<script>
  var map;

DG.then(function () {
    map = DG.map('map', {
        center: [54.993455, 73.364682],
        zoom: 13
    });

    DG.marker([54.993455, 73.364682]).addTo(map).bindPopup('Омск, Жукова 32А');
});
</script>

<div data-scroll-section class=" sm:w-full pt-5 sm:mt-0 bg-white sm:h-screen">
	<div class="sm:py-16 sm:px-32 px-4  flex-col sm:flex sm:w-full">
		<div class="sm:flex justify-between items-center">
            <div>
                <h2 class="font-medium text-3xl sm:text-[40px] sm:leading-[2.9rem]">Контакты</h2>
                <div class="pt-14">
                    <p class="pb-2">Офис</p>
                    <h1 class=" font-medium">Омск, Жукова 32А</h1>
                </div>
                <div class="pt-7">
                    <p class="pb-2">Телефон</p>
                    <h1 class=" font-medium">+7 (3812) 20-90-35</h1>
                </div>
                <div class="pt-7">
                    <p class="pb-2">Время работы</p>
                    <h1 class=" font-medium">Ежедневно с 08:30 до 24:00</h1>
                </div>
            </div>
            <div id="map" class="w-full sm:w-1/2 sm:h-[500px] h-96 mt-20 sm:mt-0"></div>
        </div>
		<div class="mt-32 flex justify-between">
			
		</div>
	</div>
</div>

<style>
</style>
