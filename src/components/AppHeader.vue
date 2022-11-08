<script>
export default {
    name: "AppHeader",
    data() {
        return {
            links: [
                {
                    title: "Home",
                    href: "/home",
                    active: false,
                },
                {
                    title: "Prodotti",
                    href: "/products",
                    active: true,
                },
                {
                    title: "Chi siamo",
                    href: "/about",
                    active: false,
                },
                {
                    title: "Contatti",
                    href: "/contacts",
                    active: false,
                }
            ]
        }
    }
}
</script>

<template>
    <header class="header">
        <div class="logo">
            <img src="../assets/img/la-molisana-logo.png" alt="Logo molisana">
        </div>
        <nav class="header-navigation">
            <ul>
                <li v-for="(link, index) in links" :key="index">
                    <a :class="{ 'active': link.active }" :href="link.href">{{ link.title }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/mixins" as *;
@use "../styles/partials/variables" as *;

.header {
    .logo {
        @include flex-center("horizontal");
    }

    &-navigation {
        ul {
            list-style: none;
            @include flex-center("horizontal");

            li {
                margin: 0px 1rem;

                a {
                    padding: .5rem 1rem;
                    background-color: lighten($primary-color, 60%);

                    &:hover,
                    &.active {
                        background-color: lighten($primary-color, 30%);
                    }
                }
            }
        }
    }

}
</style>
