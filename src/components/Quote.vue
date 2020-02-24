<template>
        <div class="col-sm-6 col-md-4 col-lg-3">
            <div class="card card-default">
                <div class="card-body quote">
                    <div class="mt">
                        <slot></slot>
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .card-body {
        font-family: Arial, Helvetica, sans-serif;
        font-size: 24px;
        color: #6e6e6e;
    }
    .quote {
        cursor: pointer;
    }
    .quote:hover {
        background: #ffe2e2;
    }

    .card {
        height: 200px !important;
        display: flex !important;
        text-align: center;
        margin-bottom: 10px;
        box-shadow: 7px 10px 12px -5px rgba(0, 0, 0, 0.56);
    }

    .mt {
        padding-top: 40px;
    }
</style>