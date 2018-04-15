<template>
    <div id="app">
        <div class="hello">
            <h1>Welcome to TodoList App!</h1>
            <div class="row">
                <div class="col-3"></div>
                <div class="col-6 d-flex align-items-center my-3">
                    <input class="form-control" type="text" placeholder="Add item">
                    <button type="button" class="btn btn-primary mx-3">Add</button>
                </div>
                <div class="col-3"></div>
            </div>
            <List :list="list"></List>
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
            ]
        })
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

    .btn-add {
        padding: 0 10px;
        cursor: pointer;
        color: blue;
    }
</style>
