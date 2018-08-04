<template>
    <div class="app mx-lg-5 mx-1 mx-sm-1 mx-md-4 my-sm-1 my-lg-3 my-md-3">
        <navbar></navbar>

        <div class="container">
            <div class="row">
                <div class="col-md-12 shadow-sm p-3 mb-5 bg-white rounded mt-5">
                    <h1 class="text-center">Resize The Window To See the SidebarMenu</h1>
                </div>
            </div>
        </div>

    </div>

</template>

<script>
    import Navbar from './Navbar.vue';
    export default {
        components: {
            'navbar': Navbar
        }
    }
</script>