<template>
    <div class="request-type-select select">
        <select v-model="method">
            <option v-for="option in options"
                    :value="option"
                    v-text="option"
            ></option>
        </select>
    </div>
</template>

<script>
    export default {
        data (){
            return {
                options: [
                    'POST',
                    'GET',
                    'DELETE',
                    'PUT',
                    'PATCH',
                    'OPTIONS',
                ]
            }
        },
        props: {
            method: {
                type: String,
                require: true
            }
        },
        watch: {
            method (method){
                this.$emit('changed', method)
            }
        }
    }
</script>

<style scoped>
    .select select {
        background-color: #A8A8A8;
        border-color: #F8F8F8;
        color: #F8F8F8;
    }

    .select select:focus{
        border-color: #F8F8F8;
    }

    .select select:hover{
        border-color: #F8F8F8;
    }

    .select:after {
        border: 1px solid #F8F8F8 !important;
        border-right: 0 !important;
        border-top: 0 !important;
        content: " ";
        display: block;
        height: 7px;
        pointer-events: none;
        position: absolute;
        -webkit-transform: rotate(-45deg);
        transform: rotate(-45deg);
        width: 7px;
        margin-top: -6px;
        right: 16px;
        top: 50%;
    }
</style>