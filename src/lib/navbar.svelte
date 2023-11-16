<script>
	import { browser } from '$app/environment';
	import { page } from '$app/stores';
	let navisOpen = true;

	//implementing dark and light mode switch
	let darkMode = true;

	function handleSwitchDarkMode() {
		darkMode = !darkMode;
		darkMode
			? document.documentElement.classList.add('dark')
			: document.documentElement.classList.remove('dark');
	}

	if (browser) {
		if (window.matchMedia('(prefers-color-scheme: dark)').matches) {
			document.documentElement.classList.add('dark');
			darkMode = true;
		} else {
			document.documentElement.classList.remove('dark');
			darkMode = false;
		}
	}

	export async function handlePageChange() {
		let path = $page.url.pathname;
		console.log(path);
		about = path === '/about';
		projects = path === '/projects';
		contact = path === '/contact';
		blog = path === '/blog';
	}

	const unsubscribe = page.subscribe(() => {
		handlePageChange();
	});
</script>

<div class="flex justify-center absolute bottom-5 w-screen">
	<nav
		class="w-[35%] flex justify-between items-center animate-fadeUp bg-eerie-black p-1 rounded-xl"
	>
		<div
			class="bg-rich-black flex items-center p-3 py-2 text-white rounded-lg border border-jungle-darkgreen"
		>
			<p class="border-r border-r-gray-500 pl-2 pr-6">Currently at</p>
			<div class="pl-3 relative inline-block text-left">
				<div>
					<button
						type="button"
						class="inline-flex w-full justify-center items-center gap-x-1.5 rounded-md px-3 py-2 text-white"
						id="menu-button"
						on:click={() => (navisOpen = !navisOpen)}
						aria-expanded="true"
						aria-haspopup="true"
					>
						<svg
							xmlns="http://www.w3.org/2000/svg"
							width="24"
							height="24"
							fill="#fff"
							viewBox="0 0 256 256"
							><path
								d="M216,115.54V208a8,8,0,0,1-8,8H160a8,8,0,0,1-8-8V160a8,8,0,0,0-8-8H112a8,8,0,0,0-8,8v48a8,8,0,0,1-8,8H48a8,8,0,0,1-8-8V115.54a8,8,0,0,1,2.62-5.92l80-75.54a8,8,0,0,1,10.77,0l80,75.54A8,8,0,0,1,216,115.54Z"
								opacity="0.2"
							/><path
								d="M218.83,103.77l-80-75.48a1.14,1.14,0,0,1-.11-.11,16,16,0,0,0-21.53,0l-.11.11L37.17,103.77A16,16,0,0,0,32,115.55V208a16,16,0,0,0,16,16H96a16,16,0,0,0,16-16V160h32v48a16,16,0,0,0,16,16h48a16,16,0,0,0,16-16V115.55A16,16,0,0,0,218.83,103.77ZM208,208H160V160a16,16,0,0,0-16-16H112a16,16,0,0,0-16,16v48H48V115.55l.11-.1L128,40l79.9,75.43.11.1Z"
							/></svg
						>Home
						<svg
							class={`-mr-1 h-5 w-5 text-gray-400 ${
								navisOpen ? 'rotate-0 animate-rotate180o' : 'animate-rotate180 rotate-180'
							}`}
							viewBox="0 0 20 20"
							fill="currentColor"
							aria-hidden="true"
						>
							<path
								fill-rule="evenodd"
								d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
								clip-rule="evenodd"
							/>
						</svg>
					</button>
				</div>
				<div
					class={`absolute bottom-10 mt-2 border border-jungle-darkgreen w-56 p-1 origin-top-right divide-y divide-eerie-black rounded-2xl bg-rich-black shadow-lg focus:outline-none ${
						navisOpen
							? 'transition ease-in duration-75 transform origin-bottom opacity-0 scale-95 z-[-10]'
							: 'transition ease-out duration-100 transform origin-bottom opacity-100 scale-100 z-10'
					}`}
					role="menu"
					aria-orientation="vertical"
					aria-labelledby="menu-button"
					tabindex="-1"
				>
					<a
						href="/"
						class="text-gray-100 block px-4 py-3 text-sm"
						role="menuitem"
						tabindex="-1"
						id="menu-item-0">Edit</a
					>
					<a
						href="/"
						class="text-gray-100 block px-4 py-3 text-sm"
						role="menuitem"
						tabindex="-1"
						id="menu-item-1">Duplicate</a
					>
					<a
						href="/"
						class="text-gray-100 block px-4 py-3 text-sm"
						role="menuitem"
						tabindex="-1"
						id="menu-item-2">Archive</a
					>
					<a
						href="/"
						class="text-gray-100 block px-4 py-3 text-sm"
						role="menuitem"
						tabindex="-1"
						id="menu-item-3">Move</a
					>
					<a
						href="/"
						class="text-gray-100 block px-4 py-3 text-sm"
						role="menuitem"
						tabindex="-1"
						id="menu-item-4">Share</a
					>
					<a
						href="/"
						class="text-gray-100 block px-4 py-3 text-sm"
						role="menuitem"
						tabindex="-1"
						id="menu-item-5">Add to favorites</a
					>
					<a
						href="/"
						class="text-gray-100 block px-4 py-2 text-sm"
						role="menuitem"
						tabindex="-1"
						id="menu-item-6">Delete</a
					>
				</div>
			</div>
		</div>
		<button class="mr-2 flex items-center justify-center" on:click={handleSwitchDarkMode}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				width="32"
				height="32"
				fill="#000000"
				viewBox="0 0 256 256"
				class={`${darkMode ? '' : 'hidden'} dark:fill-white transition ease-in-out delay-200`}
			>
				<path d="M184,128a56,56,0,1,1-56-56A56,56,0,0,1,184,128Z" opacity="0.2" /><path
					d="M120,40V16a8,8,0,0,1,16,0V40a8,8,0,0,1-16,0Zm72,88a64,64,0,1,1-64-64A64.07,64.07,0,0,1,192,128Zm-16,0a48,48,0,1,0-48,48A48.05,48.05,0,0,0,176,128ZM58.34,69.66A8,8,0,0,0,69.66,58.34l-16-16A8,8,0,0,0,42.34,53.66Zm0,116.68-16,16a8,8,0,0,0,11.32,11.32l16-16a8,8,0,0,0-11.32-11.32ZM192,72a8,8,0,0,0,5.66-2.34l16-16a8,8,0,0,0-11.32-11.32l-16,16A8,8,0,0,0,192,72Zm5.66,114.34a8,8,0,0,0-11.32,11.32l16,16a8,8,0,0,0,11.32-11.32ZM48,128a8,8,0,0,0-8-8H16a8,8,0,0,0,0,16H40A8,8,0,0,0,48,128Zm80,80a8,8,0,0,0-8,8v24a8,8,0,0,0,16,0V216A8,8,0,0,0,128,208Zm112-88H216a8,8,0,0,0,0,16h24a8,8,0,0,0,0-16Z"
				/></svg
			>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				width="32"
				height="32"
				fill="#0A0E11"
				viewBox="0 0 256 256"
				class={`${darkMode ? 'hidden' : ''} transition ease-in-out delay-200`}
			>
				<path
					d="M227.89,147.89A96,96,0,1,1,108.11,28.11,96.09,96.09,0,0,0,227.89,147.89Z"
					opacity="0.2"
				/>
				<path
					d="M233.54,142.23a8,8,0,0,0-8-2,88.08,88.08,0,0,1-109.8-109.8,8,8,0,0,0-10-10,104.84,104.84,0,0,0-52.91,37A104,104,0,0,0,136,224a103.09,103.09,0,0,0,62.52-20.88,104.84,104.84,0,0,0,37-52.91A8,8,0,0,0,233.54,142.23ZM188.9,190.34A88,88,0,0,1,65.66,67.11a89,89,0,0,1,31.4-26A106,106,0,0,0,96,56,104.11,104.11,0,0,0,200,160a106,106,0,0,0,14.92-1.06A89,89,0,0,1,188.9,190.34Z"
				/>
			</svg>
		</button>
	</nav>
</div>
