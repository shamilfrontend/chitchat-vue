<template>
    <div
        class="chitchat-main"
        :class="togglerightside ? 'small-sidebar': ''"
        id="content"
    >
        <div
            class="chat-content tabto"
            :class="activechat == 1 ? 'active' : ''"
        >
            <div
                class="scrolltopdirectchat messages custom-scroll"
                :class="activechatType == 1 ? 'active' : ''"
                id="chating"
                :style="chatwallpaperIndex !== 0? [{'background-image': 'url(' + chatwallpaper + ')'},styleObject]
          : chatwallpapergrandiant !== '' ? [{'background-image': chatwallpapergrandiant},styleObject] : ''"
            >
                <DirectChatHeader/>
                <DirectCustomChat/>
            </div>
            <div
                class="scrolltopgroupchat messages custom-scroll"
                :class="activechatType == 2 ? 'active' : ''"
                id="group_chat"
                :style="chatwallpaperIndex !== 0? [{'background-image': 'url(' + chatwallpaper + ')'},styleObject]
          : chatwallpapergrandiant !== '' ? [{'background-image': chatwallpapergrandiant},styleObject] : ''"
            >
                <GroupChatHeader/>
                <GroupCustomChat/>
            </div>

            <div class="message-input">
                <div class="wrap emojis-main">
                    <a
                        href="javascript:void(0)"
                        class="icon-btn btn-outline-primary button-effect mr-3 toggle-sticker outside"
                        @click="openSticker()"
                    >
                        <svg
                            id="Layer_1"
                            version="1.1"
                            xmlns="http://www.w3.org/2000/svg"
                            xlink="http://www.w3.org/1999/xlink"
                            x="0px"
                            y="0px"
                            width="2158px"
                            height="2148px"
                            viewBox="0 0 2158 2148"
                            enable-background="new 0 0 2158 2148"
                            space="preserve"
                        >
                            <path
                                fill-rule="evenodd"
                                clip-rule="evenodd"
                                fill="none"
                                stroke="#000000"
                                stroke-width="60"
                                stroke-miterlimit="10"
                                d="M699,693                        c0,175.649,0,351.351,0,527c36.996,0,74.004,0,111,0c18.058,0,40.812-2.485,57,1c11.332,0.333,22.668,0.667,34,1                        c7.664,2.148,20.769,14.091,25,20c8.857,12.368,6,41.794,6,62c0,49.329,0,98.672,0,148c175.649,0,351.351,0,527,0                        c0-252.975,0-506.025,0-759C1205.692,693,952.308,693,699,693z"
                            />
                            <path
                                fill-rule="evenodd"
                                clip-rule="evenodd"
                                d="M886,799c59.172-0.765,93.431,25.289,111,66c6.416,14.867,14.612,39.858,9,63                        c-2.391,9.857-5.076,20.138-9,29c-15.794,35.671-47.129,53.674-90,63c-20.979,4.563-42.463-4.543-55-10                        c-42.773-18.617-85.652-77.246-59-141c10.637-25.445,31.024-49,56-60c7.999-2.667,16.001-5.333,24-8                        C877.255,799.833,882.716,801.036,886,799z"
                            />
                            <path
                                fill-rule="evenodd"
                                clip-rule="evenodd"
                                d="M1258,799c59.172-0.765,93.431,25.289,111,66c6.416,14.867,14.612,39.858,9,63                        c-2.391,9.857-5.076,20.138-9,29c-15.794,35.671-47.129,53.674-90,63c-20.979,4.563-42.463-4.543-55-10                        c-42.773-18.617-85.652-77.246-59-141c10.637-25.445,31.024-49,56-60c7.999-2.667,16.001-5.333,24-8                        C1249.255,799.833,1254.716,801.036,1258,799z"
                            />
                            <path
                                fill-rule="evenodd"
                                clip-rule="evenodd"
                                d="M1345,1184c-0.723,18.71-11.658,29.82-20,41c-18.271,24.489-50.129,37.183-83,47                        c-7.333,1-14.667,2-22,3c-12.013,2.798-33.636,5.15-44,3c-11.332-0.333-22.668-0.667-34-1c-15.332-3-30.668-6-46-9                        c-44.066-14.426-80.944-31.937-110-61c-22.348-22.353-38.992-45.628-37-90c0.667,0,1.333,0,2,0c9.163,5.585,24.723,3.168,36,6                        c26.211,6.583,54.736,7.174,82,14c34.068,8.53,71.961,10.531,106,19c9.999,1.333,20.001,2.667,30,4c26.193,6.703,54.673,7.211,82,14                        C1304.894,1178.445,1325.573,1182.959,1345,1184z"
                            />
                            <polygon
                                fill-rule="evenodd"
                                clip-rule="evenodd"
                                points="668.333,1248.667 901.667,1482 941.667,1432 922.498,1237.846                         687,1210.667 "
                            />
                        </svg>
                    </a>
                    <div class="dot-btn dot-primary mr-3">
                        <a
                            href="javascript:void(0)"
                            class="icon-btn btn-outline-primary button-effect toggle-emoji"
                            @click="openEmogi()"
                        >
                            <feather
                                type="smile"
                                size="15"
                                height="15"
                            />
                        </a>
                    </div>
                    <div class="contact-poll">
                        <b-dropdown
                            size="lg"
                            variant="link"
                            toggle-class="text-decoration-none"
                            no-caret
                        >
                            <template #button-content>
                                <a
                                    href="javascript:void(0)"
                                    class="icon-btn btn-outline-primary mr-4 outside"
                                    @click="openContactcontent()"
                                >
                                    <i class="fa fa-plus" />
                                </a>
                            </template>
                            <b-dropdown-item href="javascript:void(0)">
                                <feather type="image" />
                                gallery
                            </b-dropdown-item>
                            <b-dropdown-item href="javascript:void(0)">
                                <feather type="camera" />
                                camera
                            </b-dropdown-item>
                            <b-dropdown-item href="javascript:void(0)" @click="showsnippetmodal()">
                                <feather type="code" />
                                Code Snippest
                            </b-dropdown-item>
                            <b-dropdown-item href="javascript:void(0)">
                                <feather type="user"></feather>
                                contact
                            </b-dropdown-item>
                            <b-dropdown-item href="javascript:void(0)">
                                <feather type="map-pin"></feather>
                                location
                            </b-dropdown-item>
                            <b-dropdown-item href="javascript:void(0)">
                                <feather type="clipboard"></feather>
                                document
                            </b-dropdown-item>
                            <b-dropdown-item href="javascript:void(0)" @click="showpollmodal()">
                                <feather type="bar-chart-2"></feather>
                                poll
                            </b-dropdown-item>
                            <b-dropdown-item href="javascript:void(0)">
                                <feather type="paperclip"></feather>
                                attach
                            </b-dropdown-item>
                        </b-dropdown>
                    </div>

                    <input class="setemoj"
                           id="setemoj"
                           v-model="text"
                           v-on:keyup.enter="addChat()"
                           type="text"
                           placeholder="Write your message..."/>
                    <a class="icon-btn btn-outline-primary button-effect mr-3 ml-3" href="javascript:void(0)">
                        <feather type="mic" size="15" height="15"></feather>
                    </a>
                    <button class="submit icon-btn btn-primary" :class="text ==='' ? 'disabled': ''" id="send-msg"
                            :disabled="text ===''" @click="addChat()">
                        <feather type="send" size="15" height="15"></feather>
                    </button>
                    <div class="emojis-contain" :class="showemogi ? 'open': ''">
                        <div class="emojis-sub-contain custom-scroll">
                            <ul>
                                <li
                                    v-for="(emogi, index) in emogi"
                                    :key="index"
                                    @click="addemogi(emogi.emoji)"
                                >
                                    {{ emogi.emoji }}
                                </li>
                            </ul>
                        </div>
                    </div>
                    <Stickers/>
                </div>
            </div>
        </div>

        <div class="call-content tabto" :class="activechat == 2 ? 'active' : ''"><a
            class="icon-btn btn-outline-primary button-effect mobile-back mb-3" @click="backtochat()"
            href="javascript:void(0)"><i class="ti-angle-left"> </i></a>
            <CallContent/>
        </div>

        <div class="contact-content tabto" :class="activechat == 3 ? 'active' : ''">
            <ContactContent/>
        </div>

        <CodeSnippet ref="codesnippet"/>

        <Poll ref="poll"/>
    </div>
</template>

<script>
import {mapState} from 'vuex';
import emogi from '../../data/emogi.json'
import Stickers from './stickers.vue'
import DropDown from './common/dropdown.vue'
import DirectChatHeader from './chat/DirectChat/directchatheader.vue'
import DirectCustomChat from './chat/DirectChat/directcustomchat.vue'
import CallContent from './calls/callcontent.vue'
import ContactContent from './contacts/contactcontent.vue'
import GroupChatHeader from './chat/GroupChat/groupchatheader.vue'
import GroupCustomChat from './chat/GroupChat/groupcustomchat.vue'
import CodeSnippet from '../messenger/modals/codesnippets.vue'
import Poll from '../messenger/modals/pollModal.vue'

export default {
    components: {
        Stickers,
        DropDown,
        DirectChatHeader,
        DirectCustomChat,
        CallContent,
        ContactContent,
        GroupChatHeader,
        GroupCustomChat,
        CodeSnippet,
        Poll
    },
    data() {
        return {
            text: "",
            emogi: emogi,
            emogiarray: [],
            styleObject: {
                'background-color': 'transparent',
                'background-blend-mode': 'unset',
            }
        }
    },

    watch: {
        chatwallpaperIndex() {
            this.$store.state.common.chatwallpaper = this.chatwallpaperIndex !== 0
                ? this.getImgUrl(this.allwallpaper.find((x) => x.id === this.chatwallpaperIndex).img)
                : '';
        }
    },

    methods: {
        openSticker() {
            this.$store.state.common.showemogi = false,
                this.$store.state.common.showcontactcontent = false,
                this.$store.state.common.showsticker = !this.$store.state.common.showsticker
        },
        openEmogi() {
            this.$store.state.common.showsticker = false,
                this.$store.state.common.showcontactcontent = false,
                this.$store.state.common.showemogi = !this.$store.state.common.showemogi
        },
        openContactcontent() {
            this.$store.state.common.showsticker = false,
                this.$store.state.common.showemogi = false,
                this.$store.state.common.showcontactcontent = !this.$store.state.common.showcontactcontent
        },
        showsnippetmodal() {
            this.$refs.codesnippet.show();
        },
        showpollmodal() {
            this.$refs.poll.show();
        },
        backtochat() {
            document.querySelector(".sidebar-toggle").classList.remove("mobile-menu");
        },
        addChat: function () {
            if (this.text != "") {
                if (this.activechatType == 1) {
                    this.$store.dispatch("chat/addChat", this.text);
                    var container = this.$el.querySelector(".scrolltopdirectchat");
                    setTimeout(function () {
                        container.scrollBy({top: 200, behavior: "smooth"});
                    }, 310);
                    setTimeout(function () {
                        container.scrollBy({top: 200, behavior: "smooth"});
                    }, 1100);
                } else {
                    this.$store.dispatch("groupchat/addChat", this.text);
                    var containerfluid = this.$el.querySelector(".scrolltopgroupchat");
                    setTimeout(function () {
                        containerfluid.scrollBy({top: 200, behavior: "smooth"});
                    }, 310);
                    setTimeout(function () {
                        containerfluid.scrollBy({top: 200, behavior: "smooth"});
                    }, 1100);
                }

                this.text = "";
                this.emogiarray = [];
            }
        },
        getImgUrl(path) {
            return require("@/assets/images/" + path);
        },
        addemogi(emogi) {
            if (this.text === '') {
                this.text = emogi
                this.emogiarray.push(emogi)
            } else {
                this.emogiarray.push(emogi)
                this.text = this.emogiarray.join(' ')
            }
            this.$store.state.common.showemogi = false
        }
    },

    mounted() {
        this.$store.state.common.chatwallpaper = this.chatwallpaperIndex !== 0 ? this.getImgUrl(this.allwallpaper.find((x) => x.id === this.chatwallpaperIndex).img) : '';
        this.$store.state.common.chatwallpapergrandiant = "";
        this.$store.state.common.togglerightside = true;
        var container = this.$el.querySelector(".scrolltopdirectchat");
        container.scrollTop = container.scrollHeight;
        var containerfluid = this.$el.querySelector(".scrolltopgroupchat");
        containerfluid.scrollTop = container.scrollHeight;
    },

    computed: {
        ...mapState({
            showsticker: (state) => state.common.showsticker,
            showemogi: (state) => state.common.showemogi,
            showcontactcontent: (state) => state.common.showcontactcontent,
            activechat: state => state.common.activechat,
            activechatType: (state) => state.common.activechatType,
            togglerightside: (state) => state.common.togglerightside,
            activerightsidebarmenu: (state) => state.common.activerightsidebarmenu,
            chatwallpaper: (state) => state.common.chatwallpaper,
            allwallpaper: (state) => state.common.allwallpaper,
            chatwallpapergrandiant: (state) => state.common.chatwallpapergrandiant,
            chatwallpaperIndex: (state) => state.common.chatwallpaperIndex,
        }),
    },
}
</script>
