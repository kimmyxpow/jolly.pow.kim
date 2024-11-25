<script lang="ts">
	import '../app.css';
	import confetti from 'canvas-confetti';

	let { children } = $props();

	function launchConfetti(event: MouseEvent) {
		confetti({
			particleCount: 100,
			spread: 70,
			origin: {
				x: event.clientX / window.innerWidth,
				y: event.clientY / window.innerHeight
			}
		});
	}

	$effect(() => {
		window.addEventListener('click', launchConfetti);
	});
</script>

<svelte:head>
	<!-- Primary Meta Tags -->
	<title>Jolly - A Fun, Fresh Language Compiler for JavaScript!</title>
	<meta name="title" content="Jolly - A Fun, Fresh Language Compiler for JavaScript!" />
	<meta
		name="description"
		content="The happiest way to write and compile JavaScript! 🚀 With Jolly, you can write your code in a fun, playful syntax and compile it into plain old JavaScript. Let's make coding a joyful experience again! 🌈✨"
	/>
	<meta
		name="keywords"
		content="JollyCompiler, Jolly language, Jolly programming language, Jolly to JavaScript, Compile Jolly code, Jolly transpiler, Jolly syntax, Jolly language CLI, Fun programming language, Experimental programming language, Compile to JavaScript, JavaScript transpiler, Learn programming with Jolly, Custom keywords in JavaScript, Interactive programming tools, Jolly language tutorial, Custom JavaScript keywords, Simplify JavaScript syntax, For loop with Jolly, Jolly conditionals (when, maybe, meh), Switch statement in Jolly (pick, option, fallback), Fun keywords for JavaScript, Build and run Jolly code, JavaScript compiler with custom syntax, Beginner-friendly language, Experimental JavaScript tools, Write better JavaScript, Alternative to JavaScript syntax, Jolly coding examples, Fun programming experience, Playful coding language, Interactive coding for developers, How to use Jolly programming language, Jolly language for JavaScript developers, Simplified JavaScript syntax with Jolly, Learn Jolly language step by step, Fun programming syntax for beginners, Compile Jolly code to JavaScript easily, Why use Jolly for JavaScript projects?, Experimental tools for JavaScript, Fun alternatives to JavaScript, Creative programming languages, Build CLI tools with JavaScript, Transform JavaScript with Jolly."
	/>
	<meta name="robots" content="index, follow" />
	<meta name="author" content="Abi Noval Fauzi" />

	<!-- Open Graph / Facebook -->
	<meta property="og:url" content="https://jolly.pow.kim" />
	<meta property="og:title" content="Jolly - A Fun, Fresh Language Compiler for JavaScript!" />
	<meta
		property="og:description"
		content="The happiest way to write and compile JavaScript! 🚀 With Jolly, you can write your code in a fun, playful syntax and compile it into plain old JavaScript. Let's make coding a joyful experience again! 🌈✨"
	/>
	<!-- <meta property="og:image" content={$page.data.image} /> -->

	<!-- Twitter -->
	<meta property="twitter:card" content="summary_large_image" />
	<meta property="twitter:url" content="https://jolly.pow.kim" />
	<meta property="twitter:title" content="Jolly - A Fun, Fresh Language Compiler for JavaScript!" />
	<meta
		property="twitter:description"
		content="The happiest way to write and compile JavaScript! 🚀 With Jolly, you can write your code in a fun, playful syntax and compile it into plain old JavaScript. Let's make coding a joyful experience again! 🌈✨"
	/>
	<!-- <meta property="twitter:image" content={$page.data.image} /> -->
</svelte:head>

<div class="min-h-dvh bg-gradient-to-br from-green-300 via-indigo-300 to-cyan-300 py-10">
	{@render children()}
</div>
