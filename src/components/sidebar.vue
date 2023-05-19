

<template>
    <div :class="['sidebar', { expanded: isExpanded }]">
        <div class="logo-container">
            <div class="imgText search-icon">
                <i @click="toggleSidebar" class="fa-solid fa-magnifying-glass"></i>
                <span v-if="isExpanded">
                    <form action="#">
                        <input type="search" class="search-data" placeholder="search">
                    </form>
                </span>
            </div>
            <div class="imgText">
                <i @click="toggleSidebar" :class="arrow" class="fa-solid fa-bars"></i>
                <span v-if="isExpanded"></span>
            </div>
            <div class="imgText">
                <i @click="toggleSidebar" class="fa-solid fa-house"></i>
                <span v-if="isExpanded">DeshBoard</span>
            </div>
            <!-- <div class="imgText">
                <i @click="toggleSidebar" class="fa-light fa-wrench"></i>
                <span v-if="isExpanded">Setting</span>
            </div> -->
            <div class="imgText">
                <i @click="toggleSidebar" class="fa-brands fa-youtube"></i>
                <span v-if="isExpanded">Youtube</span>
            </div>
            <!-- <div class="imgText">
                <i @click="toggleSidebar" class="fa-regular fa-messages"></i>
                <span v-if="isExpanded">Message</span>
            </div> -->
        </div>
    </div>
</template>
<script>
export default {
    name: 'SIDEBAR',
    data() {
        return {
            isExpanded: false,
        };
    },
    methods: {
        toggleSidebar() {
            this.isExpanded = !this.isExpanded;
        },
    },
};
</script>
<style scoped>
.sidebar {
    border-top-right-radius: 16px;
    /* margin-top: 58px; */
    border-top: 1px solid white;
    display: flex;
    flex-direction: column;
    align-items: left;
    background-color: gray;
    padding: 10px;
    color: beige;
    transition: width 0.3s;
    height: 100vh;
    width: 50px;
    position:fixed;
    top:65px;
}

.imgText {
    margin: 0 12px;
    display: flex;
    align-items: center;
}

.search-icon {
    display: none;
}

.fa-solid:hover {
    color: orange;
}

.fa-house:hover {
    color: orange;
}

.fa-wrench:hover {
    color: orange;
}

.fa-youtube:hover {
    color: orange;
}

.fa-messages:hover {
    color: orange;
}

.expanded {
    width: 200px;
}

.logo-container {
    display: flex;
    flex-direction: column;

}

button {
    display: block;
    width: 100%;
    padding: 5px;
    margin-top: 10px;
    justify-content: center;
}

.fa-bars {
    font-size: 28px;
    margin: 8px 0 20px 0;
    cursor: pointer;
    color: orangered;
}

.fa-brands {
    font-size: 28px;
    margin: 16px 0 20px 0;
    cursor: pointer;
}

span {
    margin-left: 12px;
}

form {
    display: flex;
    height: 34px;
    background: black;
    border-radius: 4px;
    border: 1px solid rgba(155, 155, 155, 0.2);
}

form .search-data {
    height: 100%;
    width: 180px;
    padding: 0 10px;
    color: white;
    font-weight: 500;
    background: none;
    border: none;
    font-size: 17px;
    outline: none;
}

form button {
    background: orange;
    border: none;
    cursor: pointer;
    font-size: 17px;
    color: white;
    border-radius: 2px;
    padding: 0 12px;
}

form button:hover {
    background: orange;
}

@media only screen and (max-width:500px) {
    .search-icon {
        display: block;

    }

    .fa-solid {
        font-size: 28px;
        margin: 20px 0 20px 0;
    }
}
</style>