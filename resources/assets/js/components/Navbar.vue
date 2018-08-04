<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-light bg-light sidebarNavigation"
             data-sidebarClass="navbar-light bg-light">
            <a class="navbar-brand" href="#">Buy to America</a>

            <div class="collapse navbar-collapse" id="navbarsExampleDefault">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="#">How it works
                        </a>
                    </li>
                    <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button"
                           data-toggle="dropdown" aria-haspopup="true"
                           aria-expanded="false">
                            Services
                        </a>
                        <div class="dropdown-menu" aria-labelledby="navbarDropdown">

                            <div class="ml-4 mt-3">
                                <div class="d-flex flex-row  mb-3">
                                    <div class="oval d-flex justify-content-center">
                                        <img src="img/004-airport copy.png" alt="">
                                    </div>
                                    <a class="dropdown-item" href="#"> Air Transport</a>
                                </div>
                                <div class="d-flex flex-row  mb-3">
                                    <div class="oval d-flex justify-content-center">
                                        <img src="img/001-ship.png" alt="">
                                    </div>
                                    <a class="dropdown-item" href="#"> Ocean Transport</a>
                                </div>

                                <div class="d-flex flex-row  mb-3">
                                    <div class="oval d-flex justify-content-center">
                                        <img src="img/006-transport-1.png" alt="">
                                    </div>
                                    <a class="dropdown-item" href="#"> Inland Transport</a>
                                </div>
                                <div class="d-flex flex-row mb-3">
                                    <div class="oval d-flex justify-content-center">
                                        <img src="img/car.svg" alt="">
                                    </div>
                                    <a class="dropdown-item" href="#"> Cars</a>
                                </div>
                            </div>

                        </div>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Help</a>
                    </li>
                </ul>

            </div>

            <div class="ml-auto mr-md-2 mr-sm-4 d-none d-md-block">
                <a class="btn mr-sm-4 btn-login btn-sm btn-font">Sign In
                </a>
                <a class="btn btn-sign-up btn-sm btn-font">Sign Up</a>
            </div>

            <button id="toggleButton" class="navbar-toggler" type="button" @click="open=true"
                    aria-controls="navbarNavDropdown" aria-expanded="false"
                    aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>


        </nav>
        <!-- side menu -->
        <div id="navbars" class="sideMenu navbar-light bg-light" :class="classObject">
            <div class="close-box d-flex justify-content-center" @click="open=false">
                <button @click="open=false" type="button" class="close" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                </button>
            </div>

            <div class="d-flex flex-row ml-2 mb-sm-5 mb-5 mt-3 mt-sm-3 ">
                <h2 class="text-uppercase text-left">Menu</h2>
            </div>

            <ul class="navbar-nav ml-auto">
                <li class="nav-item mb-3">
                    <a href="#" class="nav-link">How it works
                    </a>
                </li>
                <li class="nav-item mb-3">
                    <a href="#" class="nav-link">Services</a>
                    <ul class="navbar-nav sub-nav">
                        <li class="nav-item mb-2 mt-2">
                            <a href="#" class="nav-link">Air Transport</a>
                        </li>
                        <li class="nav-item mb-2">
                            <a href="#" class="nav-link">Ocean Transport</a>
                        </li>
                        <li class="nav-item mb-2">
                            <a href="#" class="nav-link">Inland Transportation</a>
                        </li>
                        <li class="nav-item mb-2">
                            <a href="#" class="nav-link">Cars</a>
                        </li>
                    </ul>
                </li>
                <li class="nav-item mb-3">
                    <a href="#" class="nav-link">Help</a>
                </li>
            </ul>
        </div>

        <div class='overlay' :class="classObject" @click="open=false" id="overlay"></div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                open: false
            }
        },
        computed: {
            classObject: function () {
                return {
                    open: this.open,
                }

            }
        },
        mounted: function () {
            this.$nextTick(function () {
                window.addEventListener('resize', this.isVisible);
            })

        },
        methods: {
            isVisible: function () {
                let toggleButton = document.getElementById('toggleButton');
                let overlay = document.getElementById('overlay');
                let navbars = document.getElementById('navbars');
                let offsetHeight = toggleButton.offsetHeight; // 0 if hidden , more than 0 if shown
                if (offsetHeight === 0) {
                    overlay.style.display = 'none';
                    navbars.style.display = 'none';
                } else {

                    overlay.removeAttribute('style');
                    navbars.removeAttribute('style');

                }
            }
        }
    }
</script>