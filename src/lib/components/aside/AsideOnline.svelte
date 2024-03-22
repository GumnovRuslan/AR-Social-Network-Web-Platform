<script>
    import image from '/static/user.webp?enhanced'
</script>

<div class='user'>
    <div class='user__inner'>
        <span class='user__photo'>
            <enhanced:img class="user__photo-img" src={image} alt="An alt text" />
        </span>
        <div class='user__info'>
            <p class='user__name'>Hellen Willson</p>
            <div class='user__status'>
                <span class='user__status-mark'></span>
                <span class='user__status-text'> Online</span>
            </div>
        </div>
    </div>
</div>

<style lang="scss">
    $image-size: 65px;
    .user {

        &__inner {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        &__photo {
            display: block;
            width: $image-size;
            height: $image-size;
            border-radius: 16px;
            overflow: hidden;
        }

        &__photo-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: 50% 50%;
        }

        &__info {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        &__name {
            color: #fff;
        }

        &__status {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        &__status-mark {
            display: inline-block;
            width: 10px;
            height: 10px;
            background: #40ff2f;
            border-radius: 50%;
        }

        &__status-text {
            color: #fff;
        }

    }
</style>
