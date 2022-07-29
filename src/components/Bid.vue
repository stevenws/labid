<script>
export default {
    data()
    {
        return {
            people: 4,
            marketValue: 100
        };
    },
    computed: {
        mad()
        {
            return (this.people - 1) / (this.people + 1/10) * 19/22 * this.marketValue;
        },
        careful()
        {
            return (this.people - 1) / (this.people - 1/11) * 19/22 * this.marketValue;
        },
        safe()
        {
            return (this.people - 1) / (this.people + 1/10) * 19/20 * this.marketValue;
        },
        even()
        {
            return (this.people - 1) / this.people * 19/20 * this.marketValue;
        },
        kind()
        {
            return (this.people - 1) / (this.people - 1/11) * 19/20 * this.marketValue;
        }
    }
}
</script>

<template>
    <div class="columns pb-3">
        <div class="column">
            <div class="field">
                <div class="control has-icons-left">
                    <input class="input is-large"
                           type="number"
                           v-model="people" />

                    <span class="icon is-left">
                        <font-awesome-icon icon="fa-solid fa-people-carry-box" />
                    </span>
                </div>
            </div>
        </div>

        <div class="column">
            <div class="field">
                <div class="control has-icons-left">
                    <input class="input is-large"
                           type="number"
                           v-model="marketValue" />

                    <span class="icon is-left">
                        <font-awesome-icon icon="fa-solid fa-coins" />
                    </span>
                </div>
            </div>
        </div>
    </div>

    <div class="level">
        <div class="level-item has-text-centered">
            <div>
                <p class="heading">mad</p>
                <p class="title">{{ mad.toLocaleString() }}</p>
            </div>
        </div>

        <div class="level-item has-text-centered">
            <div>
                <p class="heading">careful</p>
                <p class="title">{{ careful.toLocaleString() }}</p>
            </div>
        </div>

        <div class="level-item has-text-centered">
            <div>
                <p class="heading">safe</p>
                <p class="title">{{ safe.toLocaleString() }}</p>
            </div>
        </div>

        <div class="level-item has-text-centered">
            <div>
                <p class="heading">even</p>
                <p class="title">{{ even.toLocaleString() }}</p>
            </div>
        </div>

        <div class="level-item has-text-centered">
            <div>
                <p class="heading">kind</p>
                <p class="title">{{ kind.toLocaleString() }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.be
{
    font-size: 200%;
}
</style>
