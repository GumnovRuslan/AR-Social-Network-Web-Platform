<script>
    import Button from "../lib/components/Button.svelte";
    import {plus_square} from '../lib/icons.js'

    let icon = {
        icon: plus_square,
        color: '#f5f5f5',
        size: [20, 20]
    }
</script>

<section class='freed'>
    <div class='freed__header'>
        <h1 class='freed__title'>Freed</h1>
        <div class='freed__create'>
            <input type='text' class='freed__create-input' placeholder="Create new post">
            <Button {...icon}/>
        </div>
    </div>
</section>

<style lang="scss">
    .freed {
        display: flex;
        flex-direction: column;

        &__header {
        }

        &__title {
            font-size: 46px;
            color: #fff;
            margin-bottom: 30px;
        }

        &__create {
            display: flex;
            gap: 15px;
        }

        &__create-input {
            width: 100%;
            height: 40px;
            background: #4e4e4e44;
            border-radius: 10px;
            border: none;
            box-shadow: inset 0 2px 5px 1px #444444;
            backdrop-filter: opacity(0%);
            padding: 0 20px;
            font-size: 18px;
            color: #ececec;

            &::placeholder {
                color: #a7a7a7;
            }
        }
    }
</style>
