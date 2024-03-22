<script>
    import { onMount } from "svelte";
    export let icon = '';
    export let color = '';
    export let size = [30, 30];
    onMount(() => {

    })
</script>

<button class='button'>
    <span class='button__icon'
        style:color
        style:width={size[0]}px
        style:height={size[1]}px>
        {@html icon}
    </span>
</button>

<style lang="scss">
    .button {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 40px;
        height: 40px;
        border-radius: 10px;
        background: var(--color-btn-primary);

        &__icon {
        }
    }
</style>
