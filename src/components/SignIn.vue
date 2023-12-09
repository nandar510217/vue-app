<template>
    <div>
        <div class="row">
            <div class="col-md-6">
                <div class="card w-75">
                    <div class="card-header">
                        <h4>Sign In</h4>
                    </div>
                    <div class="card-body">
                        <form action="">
                            <div class="mb-3">
                                <input type="text" class="form-control" placeholder="Email">
                            </div>
                            <div class="mb-3">
                                <input type="text" class="form-control" placeholder="Password">
                            </div>
                            <Button btnName="Sign In" someClasses="btn-success"/>
                        </form>
                    </div>
                </div>
            </div>
            <div class="col-md-6">
                <div class="card w-75">
                    <div class="card-header">
                        <h4>Sign Up</h4>
                    </div>
                    <div class="card-body">
                        <form action="">
                            <div class="mb-3">
                                <input type="text" class="form-control" placeholder="Name">
                            </div>
                            <div class="mb-3">
                                <input type="text" class="form-control" placeholder="Email">
                            </div>
                            <div class="mb-3">
                                <input type="text" class="form-control" placeholder="Password">
                            </div>
                            <Button btnName="Sign Up" someClasses="btn-danger"/>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import {computed, ref, reactive} from 'vue';
    import Button from './Button.vue'

</script>

<style scoped>

</style>