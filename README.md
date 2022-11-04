## Getting Started - GMBN Home Page for Mobile (Infinite Scrolling feature)

### Prerequisites

For this project you need [__Node__](https://nodejs.org/en/) installed on your machine with [__Npm__](https://www.npmjs.com/) or [__Yarn__](https://yarnpkg.com)

### Installing

You can clone this repository using __Git__:
```bash
git clone https://github.com/sandesh-rai/gmbn-home-mobile.git
```

Or download the repository [here](https://github.com/sandesh-rai/gmbn-home-mobile/archive/refs/heads/main.zip)

---

Open a terminal and type, inside the directory:
```bash
npm install 
# OR
yarn install
```

for installing all the dependencies. At the end type, in the same folder:
```bash
npm run serve
# OR
yarn serve
```
for running the Vue.js development server. It will be up and running at this address: http://localhost:8080

---

### Features Implemented

* Infinite scrolling
  * This page-design approach automatically loads new videos when the user is at the bottom of the page.
  * This replaces the action of the 'Show more' button previously at the bottom of the page.
  * This is similar to other video apps like YouTube show content to users.

* Drop-down menu for viewing archives (doesn't make an API call currently)
  * The archive for viewing past videos has been moved to a more convenient location as a drop-down menu at the top of the page.
  * This is a more familiar location as options for filtering by different criteria are usually located near to the search bar.

### Future Improvements

* Side menu modifications
  * Triggered by selecting hamburger icon on the left side of mobile navbar
  * Move GMBN shop into this menu as an option (similar to https://www.globalcyclingnetwork.com/)
  * Move social media icons into the bottom of the side menu

* Options menu modal
  * Would be triggered by selecting 3 dots icon on the right side of mobile navbar
  * This accommodates the content of the footer that was replaced by inifinte scrolling feature
  * Would open a modal with links previously on the footer such as Privacy Policy, Terms & Conditions, etc

* Improve styling of drop-down menu

* Filter button next to search bar to filter with options such as 'Sort By', or to toggle visibility of archive drop-down menu

---

### Screenshot
<img src="https://github.com/sandesh-rai/gmbn-home-mobile/blob/main/src/assets/Screenshot.jpg" style='height: 450px; margin-right:20px'>

