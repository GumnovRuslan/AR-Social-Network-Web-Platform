<script>
	import {activeItem} from '../../stores/store'
	export let text = ''
	export let icon = ''

	let isActive = false

	const unsubscribe = activeItem.subscribe((value) => {
		isActive = value == text;
	});
</script>

<button class='item' class:item--active={isActive} on:click={() => activeItem.set(text)}>
	<span class='item__icon' class:item__icon--active={isActive}>{@html icon}</span>
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
			color: #adadad;
			transition: 0.2s;

			&--active {
				color: #f5f5f5 !important;
			}
    }

		&__text {
			font-size: 18px;
			color: #fff;
		}
	}
</style>
