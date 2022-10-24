<template>
    <header>
        <nav>
            <button class="navbar-hamburger-button">
                <svg aria-label="e70475f1-d37c-4882-881b-4d1b6ce9ff33" viewBox="0 0 24 24" role="img" width="24" fill="#FFFFFF" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M2 12a1 1 0 0 1 1-1h18a1 1 0 1 1 0 2H3a1 1 0 0 1-1-1ZM2 6a1 1 0 0 1 1-1h18a1 1 0 1 1 0 2H3a1 1 0 0 1-1-1ZM2 18a1 1 0 0 1 1-1h18a1 1 0 1 1 0 2H3a1 1 0 0 1-1-1Z"></path></svg>
            </button>
            <a class="navbar-brand" href="/">
                <img class="logo--mobile" src="../assets/gmbnLogo-text.svg" alt="GMBN Logo"/>
            </a>
        </nav>
    </header>
</template>

<script>
export default {

}
</script>

<style scoped>
header {
    background-color: #000;
}

header img.logo--mobile {
    padding: 1rem 0.5rem;
    width: 5rem;
}

nav {
    max-width: 75rem;
    margin-right: auto;
    margin-left: auto;
    display: flex;
    flex-flow: row wrap;
}

header a.navbar-brand {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    margin-left: auto;
    margin-right: auto;
}

header button.navbar-hamburger-button {
    background-color:transparent;
    position: absolute;
    padding: 0.5rem;
}
</style>