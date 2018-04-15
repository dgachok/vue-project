<template>
    <table class="table">
        <tbody>
        <tr v-for="item in list"
            :key="item.id">
            <th scope="row"
                width="80%"
                class="align-middle">
                {{item.text}}
            </th>
            <td width="20%">
                <button @click="done(item)"
                        type="button"
                        class="btn btn-success mx-2">Done</button>
                <button @click="remove(item)"
                        type="button"
                        class="btn btn-danger mx-2">Remove item</button>
            </td>
        </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        name: 'List',
        props: {
            list: Array
        },
        methods: {
            remove: function (item) {
                this.$emit('remove', item);
            },
            done: function (item) {
                this.$emit('done', item);
            }
        }
    }
</script>

<style scoped>
</style>
