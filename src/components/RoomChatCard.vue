<template>
    <div
        v-if="message.user.email !== user.email"
        class="user-others w-3/4 overflow-auto"
    >
        <img
            class="h-12 w-12 rounded-full object-cover mr-4"
            :src="message.user.imageUrl"
            alt=""
            v-tooltip="message.user.email"
        />
        <p class="user-text-others">{{ message.message }}</p>
    </div>

    <div v-else class="user-self w-3/4 overflow-auto">
        <p class="user-text-self">{{ message.message }}</p>
        <img
            class="h-12 w-12 rounded-full object-cover ml-4"
            :src="message.user.imageUrl"
            alt=""
            v-tooltip="message.user.email"
        />
    </div>
</template>

<script>
export default {
    name: "RoomChatCard",
    props: ["message"],
    computed: {
        user() {
            // console.log(this.$store.state.user, "ini user kamu");
            // console.log(this.message);
            return this.$store.state.user;
        },
    },
};
</script>

<style>
</style>