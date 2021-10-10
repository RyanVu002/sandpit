<template>
    <div class="user-dashboard">
        <div class="about-section">
            <h4>OUR TEAM</h4>
            <p>
                Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
                Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
                when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
                It has survived not only five centuries, but also the leap into electronic typesetting, 
                remaining essentially unchanged. 
                It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, 
                and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
            </p>
        </div>
        <div class="list-user" id="listUser">
            <div v-for="user in userData.results" :key="user.id.value">
                <UserFrame :userDetailInfo="user"></UserFrame>
            </div>
        </div>
    </div>
</template>

<script>
    //import data from './data.json'
    import axios from 'axios';
    import UserFrame from './UserFrame.vue'
    export default {
        components: {
            UserFrame
        },
        data() {
            return {
                userData: [],
                errors: []
            };
        },
        
        created() {
            axios.get(`https://randomuser.me/api/`).then(response => {
                this.userData = response.data
            })
            .catch(e => {
                this.errors.push(e)
            })
        },
    }
</script>

<style lang="scss" scoped>
    .about-section {
        padding: 50px 15%;
        text-align: center;
        color: black;
    }
    .list-user{
        padding: 50px 10%;
        text-align: center;
    }
</style>