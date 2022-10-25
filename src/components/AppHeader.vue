<template>
    <header>
        <nav>
            <button class="navbar-button">
                <svg aria-label="e70475f1-d37c-4882-881b-4d1b6ce9ff33" viewBox="0 0 24 24" role="img" width="24" fill="#FFFFFF" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M2 12a1 1 0 0 1 1-1h18a1 1 0 1 1 0 2H3a1 1 0 0 1-1-1ZM2 6a1 1 0 0 1 1-1h18a1 1 0 1 1 0 2H3a1 1 0 0 1-1-1ZM2 18a1 1 0 0 1 1-1h18a1 1 0 1 1 0 2H3a1 1 0 0 1-1-1Z"></path></svg>
            </button>
            <a class="navbar-brand" href="/">
                <img class="logo--mobile" src="../assets/gmbnLogo-text.svg" alt="GMBN Logo"/>
            </a>
            <button class="navbar-button">
                <i class="fa-solid fa-ellipsis-vertical navbar-options"></i>
            </button>
        </nav>

        <form>
            <input type="text" placeholder="Search"/>
        </form>

        <select v-model="selectedArchive">
            <option disabled value="">Please Select Archive</option>
            <option value="Latest Videos">Latest Videos</option>
            <option v-for="archive in archives" :key="archive.id" :value="archive.value">{{archive.value}}</option>
        </select>
        
    </header>
</template>

<script>
export default {
    data() {
        return {
            selectedArchive: 'Latest Videos',
            archives: [
                {
                    id: 1,
                    value: 'October 2022'
                },
                {
                    id: 2,
                    value: 'September 2022'
                },
                {
                    id: 3,
                    value: 'August 2022'
                },
                {
                    id: 4,
                    value: 'July 2022'
                },
                {
                    id: 5,
                    value: 'June 2022'
                }
            ]
        }
    },
    watch: {
        selectedArchive: {
            handler(newVal) {
                this.$emit('archiveSelected', newVal);
            },
            immediate: true
            }
        }
}
</script>

<style scoped>
header nav {
    background-color: #000;
}

header img.logo--mobile {
    padding: 1rem 0.5rem;
    width: 5rem;
}

nav {
    margin-right: auto;
    margin-left: auto;
    display: flex;
    min-width: 10rem;
}

header a.navbar-brand {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    margin-left: auto;
    margin-right: auto;
}

header button.navbar-button {
    background-color:transparent;
    padding: 0.5rem;
    cursor: pointer;
    border: none;
}

button.navbar-button i.navbar-options {
    color: #fff;
    font-size: 1rem;
    padding: 0.5rem;
}

header form {
    margin: 0.75 1em;
    display: flex;
}

header form > input{
    width: 95%;
    height: 2em;
    font-size: 1em;
    font-weight: 700;
    border-radius: 3.25em;
    border: 0.125em solid rgb(246, 246, 246);
    box-shadow: rgb(0 0 0 / 12%) 0px 0.25em 0.25em;
    text-indent: 1em;
    margin: 0.75em auto 0.25em;
}

header select {
    display: flex;
    margin: 0.5rem 0.5rem 0 auto;
}
</style>