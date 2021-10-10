<template>
    <div class="column">
        <div class="card">
        <img :src="userDetailInfo.picture.large" alt="Mike" class="avatar">
        <div class="container">
            <h2>{{userDetailInfo.name.title}}. {{userDetailInfo.name.first}} {{userDetailInfo.name.last}}</h2>
            <p class="title">{{userDetailInfo.position}}</p>
            <p class="email" :href="userDetailInfo.email">{{userDetailInfo.email}}</p>
            <p class="button-outside"><button class="button">View Detail</button></p>
        </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            userDetailInfo: {
                type: Object
            }
        },
    }
</script>

<style lang="scss" scoped>
    .avatar {
        object-fit: cover;
        border-radius:50%;
        width: 100%;
        width: 150px;
        height: 150px;
        margin: auto;
        border: 5px solid white;
    }
    .column {
        float: left;
        width: 25%;
        margin-bottom: 16px;
        padding: 0 8px;
    }
    .card {
        margin: 8px;
        border: none;
    }
    .container {
        padding: 16px;
        text-align: center;
    }
    .container::after, .row::after {
        content: "";
        clear: both;
        display: table;
    }
    .button {
        border: none;
        outline: 0;
        display: inline-block;
        padding: 8px;
        color: white;
        background-color: #4656C4;
        text-align: center;
        cursor: pointer;
        width: 65%;
    }
    .title {
        color: grey;
        white-space: nowrap;
    }
    .email {
        color: #4656C4;
        white-space: nowrap;
        cursor: pointer;
    }
</style>