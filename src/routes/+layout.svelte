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
        height: 90vh;
        display: flex;
        flex-direction: column;

        &__main {
            display: flex;
            justify-content: center;
            gap: 10px;
            height: 100%;
        }

        &__main-nav {
            flex: 1 0 auto;
            width: 100%;
            max-width: 350px;
        }

        &__main-content {
            flex: content;
            width: 100%;
            max-height: 100%;
            padding: 35px 35px;
            border-radius: 30px;
            border: 1px solid #96959580;
            background: #81818180;
            backdrop-filter: blur(20px);
        }
    }

</style>
