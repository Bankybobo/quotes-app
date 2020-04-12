<template>
    <section class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot></slot>
            </div>
        </div>       
    </section>
    
</template>

<script>
export default {
    props: ['quotes']    
}
</script>

<style scoped>
    .panel-body {
        font-family: monospace;
        font-size: 24px;
        color: rgb(212, 182, 7);
        padding: 20px;
        margin-top: 20px;
        border-radius: 10px;
        background-color: rgb(9, 9, 56);
        min-height: 200px;
    }

    .quote {
        cursor: pointer;
    }

    .quote:hover {
        color: peru;
        border: 1px solid rgb(9, 9, 56);
        background-color: wheat;
        color: rgb(9, 9, 56);
    }

</style>