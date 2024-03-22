<script>
    import UserMini from "../UserMini.svelte";
    import Button from "../Button.svelte";
    import {heart, heartFill, bookMark, bookMarkFill, chat, chatFill} from "../../icons"

    export let text = []
    export let images = []

    let buttons = [
        {
            icon: heart,
            iconActive: heartFill,
            colorActive: '#fe6363'
        },
        {
            icon: bookMark,
            iconActive: bookMarkFill,
            colorActive: '#477bff'
        },
        {
            icon: chat,
            iconActive: chatFill,
            colorActive: '#f5f5f5'
        },
        ];
</script>

<div class="post">
    <div class="post__inner">
        <div class="post__header">
            <UserMini date={true}/>
            <div class="post__header-buttons">
                {#each buttons as button}
                    <Button {...button} size={[20, 20]}/>
                {/each}
            </div>
        </div>
        <div class="post__content">
            {#if text.length}
            <div class="post__content-message">
                {#each text as content}
                    <p class="post__content-message-text">{content}</p>
                {/each}
            </div>
            {/if}
            {#if images.length}
            <div class="post__content-images">
                {#each images as image}
                    <enhanced:img class="post__content-image" src={image} alt="An alt text" />
                {/each}   
            </div>
            {/if}             
        </div>
    </div>
</div>


<style lang="scss">
    .post {

        &__inner {
            display: flex;
            flex-direction: column;
            gap: 15px;
            padding: 15px;
            border: 1px solid #acacac;
            border-radius: 20px;
        }

        &__header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 15px;
            width: 100%;
        }

        &__header-buttons {
            display: flex;
            gap: 15px;
        }

        &__content {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        &__content-message {
            display: flex;
            flex-direction: column;
            gap: 5px;
            color: #f5f5f5;
        }

        &__content-images {
            display: flex;
            flex-wrap: wrap;
            align-items:center;
            gap: 10px;
        }

        &__content-image {
            max-width: 400px;
            width: 100%;
            height: 100%;
            object-fit: contain;
            border-radius: 20px;
        }
    }
</style>