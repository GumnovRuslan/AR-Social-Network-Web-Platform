<script>
    import AsideItem from "./AsideItem.svelte";
    import UserMini from "../UserMini.svelte";
    import {compass, search, people, chat, bell} from '../../icons.js'

    let data = [
        {
            text: 'Freed',
            icon: compass
        },
        {
            text: 'Search',
            icon: search
        },
        {
            text: 'Message',
            icon: chat
        },
        {
            text: 'Friends',
            icon: people
        },
        {
            text: 'Notification',
            icon: bell
        },
    ]

    let activeButtonId = null;

    function handleButtonClick(event) {
        activeButtonId = event.detail.id;
    }
</script>

<div class=aside>
    <div class='aside__inner'>
        <div class='aside__title'>
            <span class='aside__title-text'>to</span>
            <span class='aside__title-text'>stay</span>
        </div>
        <div class='aside__main'>
            <div class='aside__main-nav-items'>
                {#each data as content}
                    <AsideItem {...content}/>
                {/each}
            </div>
            <UserMini status={true}/>
        </div>
    </div>
</div>



<style lang="scss">
    .aside {

        &__inner {
            display: flex;
            flex-direction: column;
            width: 100%;
            padding: 40px 25px 30px;
            border-radius: 30px;
            border: 1px solid #58585880;
            background: #58585880;
            backdrop-filter: blur(20px);
        }

        &__title {
            margin-bottom: 40px;
        }

        &__title-text {
            font-size: 28px;
            text-transform: uppercase;
            font-weight: 700;

            &:first-of-type {
                color: #ffc14d;
            }
            &:last-of-type {
                color: #fff;
            }
        }

        &__main {
            display: flex;
            flex-direction: column;
            gap: 35px;
        }

        &__main-nav-items {
            display: flex;
            flex-direction: column;
            gap: 10px;
            // min-height: 500px;
        }
    }
</style>
