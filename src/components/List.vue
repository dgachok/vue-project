<template>
    <table class="table">
        <tbody>
        <tr v-for="item in list"
            v-bind:key="item.id">
            <th scope="row"
                width="80%"
                class="align-middle">
                {{item.text}}
            </th>
            <td width="20%">
                <button type="button" class="btn btn-success mx-2">Done</button>
                <button type="button" class="btn btn-danger mx-2">Remove item</button>
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
        }
    }
</script>

<style scoped>
</style>
