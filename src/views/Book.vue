<template>
    <div>
        <table>
            <tr>
                <td>编号</td>
                <td>名称</td>
                <td>作者</td>
            </tr>
            <tr v-for="info in bookInfo" v-if="info.id != 1">
                <td>{{info.id}}</td>
                <td>{{info.name}}</td>
                <td>{{info.author}}</td>
            </tr>

        </table>
    </div>
</template>

<script>
    export default {
        name: "Book",
        data(){
            return{ bookInfo:[
                    {id:1,name:'java',author:'tom'},
                    {id:2,name:'php',author:'lili'}
                ]}
            },
        created() {
            axios.get('http://127.0.0.1:8085/getAllUser').then(function (res) {
                console.log(res)
            })
        }
    }
</script>

<style scoped>

</style>