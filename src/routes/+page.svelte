<script>
    import Button from "../lib/components/Button.svelte";
    import Post from '../lib/components/feed/Post.svelte'
    import image1 from '/static/post-image.webp?enhanced'
    import image2 from '/static/post-image2.webp?enhanced'
    import {plusSquare} from '../lib/icons.js'

    let posts = [
        {
            text: [
                'I have been traveling for the last 2 months. I want to share the most interesting moments!',
                'I have been traveling for the last 2 months. I want to share the most interesting moments!'
            ],
            images: [image1, image2]
        },
        {
            text: [
                'I have been traveling for the last 2 months. I want to share the most interesting moments!',
            ],
            images: [image2]
        }
    ];
</script>

<section class='freed'>
    <div class='freed__header'>
        <h1 class='freed__title'>Freed</h1>
        <div class='freed__create'>
            <input type='text' class='freed__create-input' placeholder="Create new post">
            <Button icon={plusSquare} size={[20, 20]}/>
        </div>
    </div>
    <div class="freed__content">
        {#each posts as post}
            <Post {...post}/>
        {/each}
    </div>
</section>

<style lang="scss">
    .freed {
        display: flex;
        flex-direction: column;
        gap: 10px;
        height: 100%;

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

        &__content {
            overflow: auto;
            padding-bottom: 1px;
            height: 100%;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
    }
</style>
