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
            return (this.people - 1) / this.people * 19/20 / 1.1 * this.marketValue;
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
        <div v-for="(value, name) in {mad: mad, careful: careful, safe: safe, even: even, kind: kind}"
             class="level-item has-text-centered">
            <div>
                <p class="heading">{{ name }}</p>
                <p class="title">{{ value.toLocaleString() }}</p>
                <ol>
                    <li v-for="n in 10"
                        :class="{'has-text-success': n % 2 == 0, 'has-text-danger': n % 2 == 1}">

                        {{ (value / Math.pow(1.1, n)).toLocaleString() }}
                    </li>
                </ol>
            </div>
        </div>
    </div>
</template>

<style scoped>
ol
{
    counter-reset: ol;
}

ol li
{
    counter-increment: ol;
    list-style: none;
}

ol li:before
{
    content: counters(ol, '.') ' ';
    font-size: 0.75em;
    font-family: monospace;

    position: relative;
    top: -1px;
}
</style>
