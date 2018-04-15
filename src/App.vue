<template>
    <div id="app">
        <div class="container-fluid">
            <h1>Welcome to TodoList App!</h1>
            <div class="row">
                <div class="col-3"></div>
                <div class="col-6 d-flex align-items-center my-3">
                    <input class="form-control"
                           type="text"
                           v-model="item"
                           placeholder="Add item">
                    <button @click="add(item)"
                            type="button"
                            class="btn btn-primary mx-3">Add</button>
                </div>
                <div class="col-3"></div>
            </div>
            <List :list="list"
                  @done="done($event)"
                  @remove="remove($event)"></List>
        </div>
    </div>
</template>

<script>
    import List from './components/List.vue'
    import 'bootstrap/dist/css/bootstrap.css'

    export default {
        name: 'app',
        components: {
            List
        },
        data: () => ({
            list: [
                {id: 0, text: 'Овощи'},
                {id: 1, text: 'Сыр'},
                {id: 2, text: 'Что там ещё люди едят?'}
            ],
            item: '',
            id: 3
        }),
        methods: {
            add: function (message) {
                if (message) {
                    this.list.push({id: this.id, text: message});
                    this.id++;
                    this.item = '';
                }
            },
            done: (event) => {
                console.log('done item', event);
            },
            remove: (event) => {
                console.log('remove item', event);
            }
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }

    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
