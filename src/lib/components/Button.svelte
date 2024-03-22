<script>
    export let icon = '';
    export let iconActive = ''
    export let color = '#f5f5f5';
    export let colorActive = '#f5f5f5';
    export let size = [30, 30];

    let isActive = false;
    $: iconColor = isActive ? colorActive : color

</script>

<button class='button' on:click={() => {if(iconActive) isActive = !isActive}}>
    <span class='button__icon' 
        class:button__icon--active={isActive}
        style:color={iconColor}
        style:width={size[0]}px
        style:height={size[1]}px>        
        {#if isActive}
            {@html iconActive}
        {:else}
            {@html icon}
        {/if}
    </span>
</button>

<style lang="scss">
    .button {
        display: flex;
        align-items: center;
        justify-content: center;
        flex: 1 0  auto;
        width: 40px;
        height: 40px;
        border-radius: 10px;
        background: var(--color-btn-primary);

        &__icon {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        &__icon--active {
            animation: active 0.4s ease-in-out 1 normal running 0s none;
        }

        @keyframes active {
            0% {
                transform: scale(50%);
            }
            25% {
                transform: scale(120%);
            }
            50% {
                transform: scale(90%);
            }
            70% {
                transform: scale(110%);
            }
            100% {
                transform: scale(100%);
            }
        }
    }
</style>
