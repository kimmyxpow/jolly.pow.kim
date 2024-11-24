<script>
	import Icon from '@iconify/svelte';
	import Highlight from 'svelte-highlight';
	import javascript from 'svelte-highlight/languages/javascript';
	import github from 'svelte-highlight/styles/github';

	const code = `lock greeting = "Hello, Jolly!";
lock pi = 3.14;

free count = 0;
free isActive = true;

pick (greeting) {
  option "Hello, Jolly!":
    console.log("This is a Jolly greeting! 🎨");
    yay;
  option "Hi, there!":
    console.log("A more casual hello. 👋");
    yay;
  fallback:
    console.log("Unknown greeting. 🤔");
}

loopy (free i = 0; i < 5; i++) {
    console.log("Counting with loopy: " + i);
}

free j = 5;
aslong (j > 0) {
    console.log("Counting down with aslong: " + j);
    j = j - 1;
}`;

	let isOpen = $state(false);
</script>

<svelte:head>
	{@html github}
</svelte:head>

<header class="sticky inset-x-0 top-4 z-40">
	<div class="container">
		<div
			class="relative flex items-center justify-between rounded-xl border-2 border-zinc-800 bg-fuchsia-300 px-6 py-2 shadow-[4px_4px_0_black]"
		>
			<div class="flex items-center gap-2">
				<svg class="size-10" viewBox="0 0 411 413" fill="none" xmlns="http://www.w3.org/2000/svg">
					<path
						d="M11.4892 32.2123L343.334 95.0831C346.799 95.7396 349.425 98.5875 349.799 102.094L381.83 402.151C382.335 406.878 378.63 411 373.876 411H10C5.58172 411 2 407.418 2 403V40.0725C2 35.0572 6.56158 31.2787 11.4892 32.2123Z"
						stroke="#27272A"
						stroke-width="4"
					/>
					<path
						d="M26 12.0725C26 5.80341 31.702 1.08029 37.8615 2.24726L369.706 65.1181C374.037 65.9387 377.32 69.4985 377.788 73.8818L409.819 373.939C410.45 379.848 405.819 385 399.876 385H36C30.4772 385 26 380.523 26 375V12.0725Z"
						fill="#FCD34D"
					/>
					<path
						d="M186.675 261.717C182.316 261.717 178.573 260.176 175.447 257.094C172.364 253.967 170.823 250.224 170.823 245.865C170.823 241.55 172.364 237.851 175.447 234.768C178.573 231.686 182.316 230.145 186.675 230.145C190.903 230.145 194.602 231.686 197.772 234.768C200.942 237.851 202.528 241.55 202.528 245.865C202.528 248.771 201.779 251.435 200.282 253.857C198.829 256.235 196.913 258.151 194.536 259.604C192.158 261.013 189.538 261.717 186.675 261.717ZM186.675 190.646C182.316 190.646 178.573 189.105 175.447 186.023C172.364 182.94 170.823 179.197 170.823 174.794C170.823 170.479 172.364 166.802 175.447 163.763C178.573 160.681 182.316 159.14 186.675 159.14C190.903 159.14 194.602 160.681 197.772 163.763C200.942 166.802 202.528 170.479 202.528 174.794C202.528 177.744 201.779 180.43 200.282 182.852C198.829 185.23 196.913 187.124 194.536 188.533C192.158 189.942 189.538 190.646 186.675 190.646ZM273.054 205.772C273.054 222.197 270.852 237.3 266.449 251.083C262.089 264.866 255.396 277.636 246.369 289.393H219.486C222.921 285.033 226.113 279.705 229.064 273.408C232.014 267.112 234.59 260.242 236.792 252.8C238.993 245.315 240.711 237.565 241.944 229.55C243.177 221.536 243.793 213.61 243.793 205.772C243.793 195.336 242.714 184.812 240.557 174.2C238.443 163.543 235.537 153.68 231.838 144.609C228.183 135.494 224.066 128.03 219.486 122.217H246.369C255.396 133.974 262.089 146.744 266.449 160.527C270.852 174.31 273.054 189.391 273.054 205.772Z"
						fill="#27272A"
					/>
				</svg>
				<span class="text-lg font-bold">Jolly</span>
			</div>
			<div>
				<button
					class="grid size-12 translate-0 place-items-center rounded-lg border-2 border-zinc-800 bg-white shadow-[4px_4px_0_black] transition-all hover:translate-x-1 hover:translate-y-1 hover:shadow-[0px_0px_0_black] focus:translate-x-1 focus:translate-y-1 focus:shadow-[0px_0px_0_black] md:hidden"
					onclick={() => (isOpen = !isOpen)}
				>
					<Icon class="text-xl" icon="pixelarticons:menu" />
				</button>
				<div
					class={`absolute inset-x-0 top-full mt-4 flex flex-col gap-6 rounded-xl border-2 bg-white p-6 shadow-[4px_4px_0_black] transition-all duration-300 md:static md:mt-0 md:flex-row md:items-center md:border-0 md:bg-transparent md:p-0 md:shadow-transparent ${!isOpen ? 'pointer-events-none -translate-y-20 scale-75 opacity-0 md:pointer-events-auto md:translate-y-0 md:scale-100 md:opacity-100' : 'pointer-events-auto translate-y-0 scale-100 opacity-100'}`}
				>
					<a
						class="relative after:absolute after:inset-x-0 after:top-full after:h-0.5 after:translate-y-1 after:rounded-full after:transition-all after:content-[''] hover:after:translate-y-0 hover:after:bg-zinc-800"
						href="https://github.com/kimmyxpow/jolly-lang"
					>
						Docs
					</a>
					<a
						class="relative after:absolute after:inset-x-0 after:top-full after:h-0.5 after:translate-y-1 after:rounded-full after:transition-all after:content-[''] hover:after:translate-y-0 hover:after:bg-zinc-800"
						href="https://discord.gg/ybanDqVTsA"
						target="_blank"
						rel="noopener noreferrer"
					>
						Discord Community
					</a>
					<a
						onclick={(e) => {
							e.preventDefault();
							alert('This feature is still in development!');
						}}
						class="relative after:absolute after:inset-x-0 after:top-full after:h-0.5 after:translate-y-1 after:rounded-full after:transition-all after:content-[''] hover:after:translate-y-0 hover:after:bg-zinc-800"
						href="/play"
					>
						Playground
					</a>
					<a
						href="https://github.com/kimmyxpow/jolly-lang"
						class="grid size-12 translate-0 place-items-center rounded-lg border-2 border-zinc-800 bg-white shadow-[4px_4px_0_black] transition-all hover:translate-x-1 hover:translate-y-1 hover:shadow-[0px_0px_0_black] focus:translate-x-1 focus:translate-y-1 focus:shadow-[0px_0px_0_black]"
						target="_blank"
						rel="noopener noreferrer"
					>
						<Icon class="text-xl" icon="pixelarticons:github" />
					</a>
				</div>
			</div>
		</div>
	</div>
</header>
<main class="mt-10">
	<div class="container grid items-start gap-6 md:grid-cols-2">
		<div class="order-2 grid gap-6 md:order-1">
			<div class="rounded-xl border-2 bg-sky-300 p-10 shadow-[4px_4px_0_black]">
				<h1 class="text-6xl font-bold">Code Joyfully with Jolly 🎉</h1>
			</div>
			<div class="grid items-start gap-6 xl:grid-cols-2">
				<div class="rounded-xl border-2 bg-lime-300 p-10 shadow-[4px_4px_0_black]">
					<p class="text-xl">
						Jolly makes JavaScript fun again! Write code in a playful, easy-to-read syntax and let
						Jolly handle the boring stuff—converting it to JavaScript. 🚀
					</p>
				</div>
				<div
					class="flex flex-col justify-between gap-6 rounded-xl border-2 bg-pink-300 p-10 shadow-[4px_4px_0_black]"
				>
					<a
						onclick={(e) => {
							e.preventDefault();
							alert('This feature is still in development!');
						}}
						href="/play"
						class="grid h-16 translate-0 place-items-center rounded-lg border-2 border-zinc-800 bg-white px-6 text-lg shadow-[4px_4px_0_black] transition-all hover:translate-x-1 hover:translate-y-1 hover:shadow-[0px_0px_0_black] focus:translate-x-1 focus:translate-y-1"
					>
						Try Jolly Playground 🚀
					</a>
					<a
						href="https://github.com/kimmyxpow/jolly-lang"
						class="grid h-16 translate-0 place-items-center rounded-lg border-2 border-zinc-800 bg-white px-6 text-lg shadow-[4px_4px_0_black] transition-all hover:translate-x-1 hover:translate-y-1 hover:shadow-[0px_0px_0_black] focus:translate-x-1 focus:translate-y-1"
						target="_blank"
						rel="noopener noreferrer"
					>
						Dive Into the Docs 📖
					</a>
				</div>
			</div>
			<div class="overflow-x-auto rounded-xl border-2 bg-violet-300 p-10 shadow-[4px_4px_0_black]">
				<p class="text-xl">
					Let’s bring some joy back into coding with Jolly! 🎉💻 But remember, don’t take this too
					seriously—it’s just for fun! 😉
				</p>
			</div>
		</div>
		<div
			class="order-1 overflow-x-auto rounded-xl border-2 bg-white p-10 shadow-[4px_4px_0_black] md:order-2"
		>
			<Highlight language={javascript} {code} />
		</div>
	</div>
</main>
