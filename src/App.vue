<template>
    <div id="app">
        <mt-header title="通訊錄">
            <mt-button icon="back" slot="left">返回</mt-button>
            <mt-button icon="more" slot="right"></mt-button>
        </mt-header>
        <mt-index-list>
            <!-- <mt-index-section index="A">
                <mt-cell title="Aaron"></mt-cell>
                <mt-cell title="Alden"></mt-cell>
                <mt-cell title="Austin"></mt-cell>
            </mt-index-section> -->
            <mt-index-section v-for="item in userData" :index="item.index" :key="item.index">
                <mt-cell
                    v-for="(user, id) in item.users"
                    @click.native="telAlert(user.tel)"
                    :title="user.name"
                    :key="id"
                ></mt-cell>
            </mt-index-section>
        </mt-index-list>
    </div>
</template>

<script>
    import { MessageBox } from 'mint-ui'
    var userData = [
        {
            index: 'A',
            users: [
                { name: 'a1', tel: '0912111111' },
                { name: 'a2', tel: '0912111112' },
                { name: 'a3', tel: '0912111113' },
                { name: 'a4', tel: '0912111114' },
                { name: 'a5', tel: '0912111115' },
                { name: 'a6', tel: '0912111116' }
            ]
        },
        {
            index: 'B',
            users: [
                { name: 'b1', tel: '0912111114' },
                { name: 'b2', tel: '0912111115' },
                { name: 'b3', tel: '0912111116' },
                { name: 'b4', tel: '0912111117' },
                { name: 'b5', tel: '0912111118' },
                { name: 'b6', tel: '0912111119' }
            ]
        },
        {
            index: 'C',
            users: [
                { name: 'c1', tel: '0912111117' },
                { name: 'c2', tel: '0912111118' },
                { name: 'c3', tel: '0912111119' },
                { name: 'c4', tel: '0912111117' },
                { name: 'c5', tel: '0912111118' },
                { name: 'c6', tel: '0912111119' }
            ]
        },
        {
            index: 'D',
            users: [
                { name: 'd1', tel: '0912111121' },
                { name: 'd2', tel: '0912111122' },
                { name: 'd3', tel: '0912111123' },
                { name: 'd4', tel: '0912111121' },
                { name: 'd5', tel: '0912111122' },
                { name: 'd6', tel: '0912111123' }
            ]
        },
        {
            index: 'E',
            users: [
                { name: 'e1', tel: '0912111124' },
                { name: 'e2', tel: '0912111125' },
                { name: 'e3', tel: '0912111126' },
                { name: 'e4', tel: '0912111124' },
                { name: 'e5', tel: '0912111125' },
                { name: 'e6', tel: '0912111126' }
            ]
        },
        {
            index: 'F',
            users: [
                { name: 'f1', tel: '0912111127' },
                { name: 'f2', tel: '0912111128' },
                { name: 'f3', tel: '0912111129' },
                { name: 'f4', tel: '0912111127' },
                { name: 'f5', tel: '0912111128' },
                { name: 'f6', tel: '0912111129' }
            ]
        }
    ]

    export default {
        name: 'App',
        data() {
            return {
                userData: userData
            }
        },
        methods: {
            telAlert: function(tel) {
                MessageBox({
                    title: '撥打',
                    message: tel,
                    showCancelButton: true
                })
            }
        }
    }
</script>

<style>
    * {
        margin: 0;
        padding: 0;
    }
</style>
