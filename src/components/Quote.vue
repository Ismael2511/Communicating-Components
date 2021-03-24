<template>
    <div class="col-sn-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot name="quote"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['quotes']
}
</script>

<style>
    .panel-body{
        font-family: 'Arizona', cursive;
        font-size: 24px;
        counter-reset: #6e6e6e;
    }
    .quote {
        cursor: pointer;
    }
    .quote:hover{
        background:rgba(255, 0, 0, 0.24);
    }
</style>