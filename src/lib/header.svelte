<script>
	import 'ninja-keys';
	import { onMount } from 'svelte';
	let hotkeys = [
		{
			id: 'Navigate Page',
			title: 'Navigate to A Certain Page',
			children: ['Metric Units', 'Imperial Units']
			// icon: '<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="#fff" viewBox="0 0 256 256"><path d="M152,138V48a32,32,0,0,0-64,0v90a56,56,0,1,0,64,0Zm-32,70a24,24,0,1,1,24-24A24,24,0,0,1,120,208Z" opacity="0.2"></path><path d="M212,56a28,28,0,1,0,28,28A28,28,0,0,0,212,56Zm0,40a12,12,0,1,1,12-12A12,12,0,0,1,212,96Zm-84,57V88a8,8,0,0,0-16,0v65a32,32,0,1,0,16,0Zm-8,47a16,16,0,1,1,16-16A16,16,0,0,1,120,200Zm40-66V48a40,40,0,0,0-80,0v86a64,64,0,1,0,80,0Zm-40,98a48,48,0,0,1-27.42-87.4A8,8,0,0,0,96,138V48a24,24,0,0,1,48,0v90a8,8,0,0,0,3.42,6.56A48,48,0,0,1,120,232Z"></path></svg>',
		},
		{
			id: 'Home',

			keywords: 'home',
			parent: 'Units',
			handler: () => {
				console.log("haha let's gooo not america");
				let ninja = document.querySelector('ninja-keys');
				ninja.close();
			}
		},
		{
			id: 'About',
			title: 'Change units to Imperial system',
			hotkey: 'ctrl+i',
			keywords: 'imperial',
			parent: 'Units',
			handler: () => {
				let ninja = document.querySelector('ninja-keys');
				ninja.close();
			}
		},
		{
			id: 'Performance Mode',
			title: 'Start/Stop Live Wallpapers...',
			// icon: '<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="#fff" viewBox="0 0 256 256"><path d="M132.37,134.59,44.18,190.74A7.91,7.91,0,0,1,32,184.15V71.85a7.91,7.91,0,0,1,12.18-6.59l88.19,56.15A7.8,7.8,0,0,1,132.37,134.59Z" opacity="0.2"></path><path d="M184,64V192a8,8,0,0,1-16,0V64a8,8,0,0,1,16,0Zm40-8a8,8,0,0,0-8,8V192a8,8,0,0,0,16,0V64A8,8,0,0,0,224,56Zm-80,72a15.76,15.76,0,0,1-7.33,13.34L48.48,197.49A15.91,15.91,0,0,1,24,184.15V71.85A15.91,15.91,0,0,1,48.48,58.51l88.19,56.15A15.76,15.76,0,0,1,144,128Zm-16.18,0L40,72.08V183.93Z"></path></svg>',
			children: ['Start Live Wallpapers', 'Stop Live Wallpapers']
		},
		{
			id: 'Stop Live Wallpapers',
			title: 'Stop live wallpaper',
			hotkey: 'ctrl+p',
			parent: 'Performance Mode',
			handler: () => {
				console.log('FURRFORMANCEEEEEEEEE');
				let ninja = document.querySelector('ninja-keys');
				ninja.close();
			}
		},
		{
			id: 'Start Live Wallpapers',
			title: 'Start live wallpaper',
			hotkey: 'ctrl+o',
			parent: 'Performance Mode',
			handler: () => {
				console.log('NO FURRFORMANCEEEEEEEEE');
				let ninja = document.querySelector('ninja-keys');
				ninja.close();
			}
		}
	];
	onMount(async () => {
		let ninja = document.querySelector('ninja-keys');
		ninja.data = hotkeys;
		console.log('workey');
	});
</script>

<header class="absolute w-screen p-7 px-10 grid grid-cols-3 animate-fadeDown items-center">
	<div class="flex gap-5 col-span-1">
		<a href="/" class="fill-white"
			><svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 320 512"
				><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
					d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"
				/></svg
			></a
		>
		<a href="/" class="fill-white"
			><svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 448 512"
				><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
					d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
				/></svg
			></a
		>
		<a href="/" class="fill-white"
			><svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512"
				><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
					d="M389.2 48h70.6L305.6 224.2 487 464H345L233.7 318.6 106.5 464H35.8L200.7 275.5 26.8 48H172.4L272.9 180.9 389.2 48zM364.4 421.8h39.1L151.1 88h-42L364.4 421.8z"
				/></svg
			></a
		>
		<a href="/" class="fill-white"
			><svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"
				><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
					d="M232 237.2c31.8-15.2 48.4-38.2 48.4-74 0-70.6-52.6-87.8-113.3-87.8H0v354.4h171.8c64.4 0 124.9-30.9 124.9-102.9 0-44.5-21.1-77.4-64.7-89.7zM77.9 135.9H151c28.1 0 53.4 7.9 53.4 40.5 0 30.1-19.7 42.2-47.5 42.2h-79v-82.7zm83.3 233.7H77.9V272h84.9c34.3 0 56 14.3 56 50.6 0 35.8-25.9 47-57.6 47zm358.5-240.7H376V94h143.7v34.9zM576 305.2c0-75.9-44.4-139.2-124.9-139.2-78.2 0-131.3 58.8-131.3 135.8 0 79.9 50.3 134.7 131.3 134.7 61.3 0 101-27.6 120.1-86.3H509c-6.7 21.9-34.3 33.5-55.7 33.5-41.3 0-63-24.2-63-65.3h185.1c.3-4.2.6-8.7.6-13.2zM390.4 274c2.3-33.7 24.7-54.8 58.5-54.8 35.4 0 53.2 20.8 56.2 54.8H390.4z"
				/></svg
			></a
		>
		<a href="/" class="fill-white">
			<svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 496 512"
				><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path
					d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3.3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5.3-6.2 2.3zm44.2-1.7c-2.9.7-4.9 2.6-4.6 4.9.3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3.7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3.3 2.9 2.3 3.9 1.6 1 3.6.7 4.3-.7.7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3.7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3.7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z"
				/></svg
			>
		</a>
	</div>
	<div class="col-span-1 flex justify-center items-center">
		<img src="/logo.svg" alt="logo" />
	</div>

	<div class="col-span-1 flex justify-end items-center">
		<button
			class="text-[#bfbfbf] flex gap-28 py-1 px-2 items-center border bg-[#FFFFFF0D] border-gray-500 rounded-lg"
			on:click={() => {
				let ninja = document.querySelector('ninja-keys');
				ninja.open();
			}}
		>
			<div class="flex gap-3 items-center text-lg">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					width="20"
					height="20"
					viewBox="0 0 20 20"
					class="fill-gray-500"
				>
					<path
						d="M19.5306 18.4694L14.8375 13.7763C16.2004 12.1417 16.8807 10.0445 16.7368 7.92116C16.5928 5.79777 15.6358 3.81162 14.0648 2.37589C12.4937 0.940156 10.4296 0.165394 8.30189 0.212776C6.17416 0.260158 4.1466 1.12604 2.64103 2.63028C1.13546 4.13452 0.267789 6.16131 0.218527 8.289C0.169264 10.4167 0.942202 12.4815 2.37654 14.0538C3.81088 15.6261 5.79619 16.5849 7.91945 16.7307C10.0427 16.8765 12.1404 16.1981 13.7762 14.8366L18.4694 19.5307C18.5391 19.6003 18.6218 19.6556 18.7128 19.6933C18.8039 19.731 18.9015 19.7504 19 19.7504C19.0985 19.7504 19.1961 19.731 19.2872 19.6933C19.3782 19.6556 19.4609 19.6003 19.5306 19.5307C19.6003 19.461 19.6556 19.3782 19.6933 19.2872C19.731 19.1962 19.7504 19.0986 19.7504 19C19.7504 18.9015 19.731 18.8039 19.6933 18.7129C19.6556 18.6218 19.6003 18.5391 19.5306 18.4694ZM1.75 8.50003C1.75 7.165 2.14588 5.85996 2.88758 4.74993C3.62928 3.6399 4.68348 2.77473 5.91688 2.26384C7.15029 1.75295 8.50749 1.61928 9.81686 1.87973C11.1262 2.14018 12.329 2.78305 13.273 3.72706C14.217 4.67106 14.8598 5.8738 15.1203 7.18317C15.3807 8.49254 15.2471 9.84974 14.7362 11.0831C14.2253 12.3165 13.3601 13.3707 12.2501 14.1124C11.1401 14.8541 9.83502 15.25 8.5 15.25C6.7104 15.248 4.99466 14.5362 3.72922 13.2708C2.46378 12.0054 1.75198 10.2896 1.75 8.50003Z"
						fill="#CACACA"
					/>
				</svg>Search
			</div>
			<span class="p-1 px-2 rounded-md text-gray-300">Ctrl + K</span></button
		>
	</div>
	<ninja-keys placeholder="Quick Search" class="dark" noAutoLoadMdIcons />
</header>
