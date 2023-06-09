<template>
    <div class="container">
        <div class="panel">
            <div class="panel__section">
                <div class="panel__logo">
                    <img src="@/assets/img/team.svg" alt="" />
                </div>
                <div class="panel__text">
                    <span>Team</span>
                    <div class="panel__info">
                        <img src="@/assets/img/info.svg" alt="" />
                    </div>
                </div>
            </div>
            <div class="panel__data">
                <div
                    v-for="item in onlineData"
                    :key="item.name"
                    class="panel__item"
                >
                    <div class="panel__count">
                        {{ item.count }}
                        <span
                            v-if="item.online"
                            class="panel__indicator"
                        ></span>
                    </div>
                    <div class="panel__name">{{ item.name }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            onlineData: [
                { name: "members", count: 130 },
                { name: "online", count: 36, online: true },
                { name: "men", count: 50 },
                { name: "women", count: 80 },
                { name: "average age", count: 29 },
                { name: "days work on average", count: 265 },
                { name: "days work newest employee", count: 36 },
                { name: "days work oldest employee", count: 1256 },
            ],
        };
    },
};
</script>


<style scoped lang="scss">
.panel {
    max-width: 1400px;
    margin: 0 auto;
    padding-top: 28px;
    color: #2a355a;
    font-size: 14px;
    border-radius: 12px;
    display: flex;
    justify-content: space-between;
    .panel &__logo {
        width: 32px;
        height: 32px;
    }
    &__section {
        display: flex;
        align-items: center;
    }
    &__text {
        margin-left: 16px;
        position: relative;
    }
    &__info {
        width: 14px;
        height: 14px;
        position: absolute;
        right: -18px;
        top: -5px;
    }
    &__item {
        padding: 0 36px;
        border-right: 1px solid #e5e8ef;
        &:last-child {
            border: none;
        }
        &:nth-child(3) {
            border: none;
            padding-right: 0;
        }
    }
    &__data {
        display: flex;
    }
    &__indicator {
        width: 6px;
        height: 6px;
        border-radius: 50%;
        background-color: #24c182;
        position: absolute;
        right: -10px;
        top: 0;
    }
    &__count {
        display: inline-block;
        position: relative;
    }
    &__name {
        margin-top: 5px;
        font-size: 12px;
    }
}
</style>
