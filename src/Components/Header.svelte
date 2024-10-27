<!-- HEADER -->
<!-- -->
<!-- -->
<!-- -->
<!-- -->

<!-- HTML -->
<header>
    <nav class="navbar / is-warning">
        <div class="container">
            <div class="navbar-brand">
               <button class="navbar-item is-flex is-align-items-center">
                <!-- TITLE / LOGO -->
                    <h1 class="is-size-2 has-text-weight-bold has-text-white">STOP WATCH</h1>
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" width="32" height="32">
                        <path d="M256 0a256 256 0 1 1 0 512A256 256 0 1 1 256 0zM232 120l0 136c0 8 4 15.5 10.7 20l96 64c11 7.4 25.9 4.4 33.3-6.7s4.4-25.9-6.7-33.3L280 243.2 280 120c0-13.3-10.7-24-24-24s-24 10.7-24 24z"/>
                    </svg>
                </button>
                
                <a role="button" id="burgerMenu" class="navbar-burger / has-text-black" aria-label="menu" aria-expanded="false" d   ata-target="navbarMenu" href="#">
                    <!-- HAMBURGER MENU -->
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                </a>
            </div>

            <!--NAV BAR BUTTONS -->
            <div class="navbar-menu" id="nav-links">
                <!-- TEXT BUTTONS -->
                <div class="navbar-end">
                    <a class="navbar-item / has-text-white / has-text-weight-medium" id="navButton" href="#">
                        About
                    </a>
                    <a class="navbar-item / has-text-white / has-text-weight-medium" id="navButton"  href="#">
                        Blog
                    </a>
                    <a class="navbar-item / has-text-white / has-text-weight-medium" id="navButton"  href="#">
                        News
                    </a>
                </div>
            </div>
            <script>
                const burgerIcon = document.querySelector("#burgerMenu");
                const navbarMenu = document.querySelector("#nav-links");
                const navButtons = document.querySelectorAll("#navButton");

                burgerIcon.addEventListener("click", () => {
                    navbarMenu.classList.toggle("is-active");
                    burgerIcon.classList.toggle("has-text-black")
                    burgerIcon.classList.toggle("has-text-white")
                });

                navButtons.forEach(button => {
                    button.addEventListener("mouseenter", () => {
                        button.classList.toggle("has-text-white");
                        button.classList.toggle("has-text-black");
                });

                button.addEventListener("mouseleave", () => {
                    button.classList.toggle("has-text-black");
                    button.classList.toggle("has-text-white");
                });
                });
            </script>
         </div>
    </nav>
</header>
