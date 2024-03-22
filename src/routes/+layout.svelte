<script>
    import Aside from '../lib/components/aside/Aside.svelte'
</script>

<div class='page'>
    <div class='application'>
        <div class='application__header'></div>
        <div class='application__main'>
            <div class='application__main-nav'>
                <Aside/>
            </div>
            <div class='application__main-content'>
                <slot />
            </div>
        </div>

    </div>
</div>

<style lang="scss">
    .page {
        display: flex;
        align-items: center;
        justify-content: center;
        min-height: 100vh;
        background-image: url(/background.webp);
        background-position: 50%;
        background-repeat: no-repeat;
        background-size: cover;
    }

    .application {
        width: 93%;
        max-height: 100vh;
        display: flex;
        flex-direction: column;


        &__main {
            display: flex;
            justify-content: center;
            gap: 10px;
        }

        &__main-nav {
            flex: 1 0 auto;
            max-width: 350px;
        }

        &__main-content {
            flex: content;
            width: 100%;
            padding: 50px;
            border-radius: 30px;
            border: 1px solid #96959580;
            background: #81818180;
            backdrop-filter: blur(20px);
        }
    }

</style>
