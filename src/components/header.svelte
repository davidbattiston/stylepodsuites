<script>
    import Logo from "../images/stylepod-logo.png";
</script>

<header>
    <a href="/" class="logo-anchor">
        <img src={Logo} alt="Stylepod Suites Logo" />
    </a>
    <nav>
        <a href="#contact">
            <i class="gg-phone" />
            <span class="contact-text">Contact Us</span>
        </a>
    </nav>
</header>

<style lang="scss">
    @use "../node_modules/rfs/scss" as rfs;
    header {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

    nav {
        width: max-content;
        background-color: rgba(233, 135, 9, 100);
        color: #f8f8ff;
        display: flex;
        a {
            @include rfs.margin-right(24px);
            @include rfs.margin-left(24px);
            margin-top: auto;
            margin-bottom: auto;
        }
    }

    a.logo-anchor {
        display: flex;
        margin: auto 0;
        img {
            width: 100%;
            max-width: 260px;
            height: auto;
        }
    }

    .contact-text {
        display: none;
    }
    i.gg-phone {
        transform: scale(var(--ggs, 1.2));
    }

    @media only screen and (min-width: 860px) {
        i.gg-phone {
            display: none;
        }

        .contact-text {
            display: inherit;
        }

        a.logo-anchor img {
            max-width: 400px;
        }
    }
</style>
