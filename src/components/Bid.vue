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
    <form class="box">
        <div class="field">
            <label class="label">People</label>
            <div class="control">
                <input class="input" type="number" v-model="people" />
            </div>
        </div>

        <div class="field">
            <label class="label">Market Value</label>
            <div class="control">
                <input class="input" type="number" v-model="marketValue" />
            </div>
        </div>
    </form>

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
