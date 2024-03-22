<script>
	import {activeItem} from './store'
  export let text = ''
	export let icon = ''

	let isActive = false

	const unsubscribe = activeItem.subscribe((value) => {
		isActive = value == text;
	});
</script>

<button class='item' class:item--active={isActive} on:click={() => activeItem.set(text)}>
  <span class='item__icon'>{icon}</span>
  <span class='item__text'>{text}</span>
</button>

<style lang="scss">
	.item {
		display: flex;
		align-items: center;
		gap: 15px;
		padding: 15px;
		border-radius: 20px;
		transition: 0.2s;

		&:hover {
			background: #cacaca34;
		}

		&--active {
			background: #cacaca65 !important;
		}

  	&__icon {
			display: inline-block;
			width: 30px;
			height: 30px;
			background: #000;
    }

		&__text {
			font-size: 18px;
			color: #fff;
		}
  }
</style>
