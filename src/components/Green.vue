<template>
    <div class="component component--green">
        <slot name="heading"></slot>
        <slot name="content"></slot>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

.component--green {
        background-color: rgba(green, .8);
    }

.heading_green {
    font-size: 2rem;
    color: #fafafa;
}

.content_green {
    font-size: 1.6rem;
    color: #fafafa;
}


</style>
