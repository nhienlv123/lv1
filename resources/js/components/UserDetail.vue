<template>
    <div class="user-detail">
        <div class="user-detail-container">
            <div class="user-name">
                Name: {{userDetailInfo.name.last}} {{childrenSelectUser.name.first}}
            </div>
            <div class="user-email">
                Email: {{userDetailInfo.email}}
            </div>
            <div class="user-dob">
                DOB: {{userDetailInfo.dob.date}}
            </div>
            <div class="gender">
                Gender: {{userDetailInfo.gender}}
            </div>
            <div class="user-address">
                Address: {{userDetailInfo.location.city}}
            </div>
        </div>
    </div>
</template>

<script>
    import EventBus from './EventBus'
    export default {
        created() {
            EventBus.$on('userSelected',this.childrenSelectUser)
        },
        destroy() {
            EventBus.$off('userSelected',this.childrenSelectUser)
        },
        methods: {
            childrenSelectUser(user) {
                console.log('childrenSelectUser',user)
                this.userDetailInfo = user
            }
        },
        props: {
            userDetailInfo: {
                type: Object
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>