<template>
    <div class="component component--blue">
        <slot name="heading"></slot>
        <slot name="content"></slot>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

    .component--blue {
        background-color: rgba(orangered, .8);
    }

    .heading_red {
    font-size: 2rem;
    color: #fafafa;
}

    .content_red {
        font-size: 1.6rem;
        color: #fafafa;
    }


</style>
