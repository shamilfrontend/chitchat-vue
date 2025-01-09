<template>
    <aside class="chitchat-left-sidebar left-disp">
        <RecentChat/>
        <Favourite/>
        <Documents/>
        <ContactList/>
        <Notifications/>
        <Settings/>
        <Status/>
    </aside>
</template>

<script>
import RecentChat from "./lefsidebar/recentchat.vue";
import Favourite from "./lefsidebar/favourite.vue";
import Documents from "./lefsidebar/document.vue";
import ContactList from "./lefsidebar/contact_list.vue";
import Notifications from "./lefsidebar/notification.vue";
import Settings from "./lefsidebar/settings.vue";
import Status from "./lefsidebar/status.vue";

export default {
    components: {
        RecentChat,
        Favourite,
        Documents,
        ContactList,
        Notifications,
        Settings,
        Status,
    },
};
</script>
