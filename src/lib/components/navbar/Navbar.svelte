<script>
	import { Drawer, Button, CloseButton } from 'flowbite-svelte';
	import { Icon } from 'flowbite-svelte-icons';
	import { sineIn } from 'svelte/easing';
	let hidden1 = true;
	let transitionParams = {
	  x: -320,
	  duration: 200,
	  easing: sineIn
	};
  </script>
  
  <div class="text-center">
	<Button on:click={() => (hidden1 = false)}>Show drawer</Button>
  </div>
  
  <Drawer transitionType="fly" {transitionParams} bind:hidden={hidden1} id="sidebar1">
	<div class="flex items-center">
	  <h5 id="drawer-label" class="inline-flex items-center mb-4 text-base font-semibold text-gray-500 dark:text-gray-400">
		<Icon name="info-circle-solid" class="w-4 h-4 mr-2.5" />Info
	  </h5>
	  <CloseButton on:click={() => (hidden1 = true)} class="mb-4 dark:text-white" />
	</div>
	<p class="mb-6 text-sm text-gray-500 dark:text-gray-400">
	  Supercharge your hiring by taking advantage of our <a href="/" class="text-primary-600 underline dark:text-primary-500 hover:no-underline"> limited-time sale </a>
	  for Flowbite Docs + Job Board. Unlimited access to over 190K top-ranked candidates and the #1 design job board.
	</p>
	<div class="grid grid-cols-2 gap-4">
	  <Button color="light" href="/">Learn more</Button>
	  <Button href="/" class="px-4">Get access <Icon name="arrow-right-outline" class="w-3.5 h-3.5 ml-2" /></Button>
	</div>
  </Drawer>