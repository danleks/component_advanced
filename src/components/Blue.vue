<template>
    <div class="component component--blue">
        <slot name="heading"></slot>
        <slot name="content"></slot>
    </div>
</template>

<script>
export default {

    props: {
        componentHeading: {
            type: Object,
            required: true
        }
    }

}
</script>

<style lang="scss" scoped>

.component--blue {
        background-color: rgba(blue, .8);
    }

.heading_blue {
    font-size: 2rem;
    color: #fafafa;
}

.content_blue {
    font-size: 1.6rem;
    color: #fafafa;
}

</style>
