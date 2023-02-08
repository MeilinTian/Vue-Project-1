<template>
    <table class="table table-bordered table-stripped">
        <thead>
            <tr>
                <!-- <th>#</th>
                <th>商品名称</th>
                <th>价格</th>
                <th>标签</th>
                <th>操作</th> -->
                <slot name="header"></slot>
            </tr>
        </thead>
        <tbody class="my-goods-list">
            <tr 
                v-for="(obj, index) in arr"
                :key="index">
                <!-- <td>{{obj.id}}</td>
                <td>{{obj.goods_name}}</td>
                <td>{{obj.goods_price}}</td>
                <td>{{obj.tags}}</td>
                <td>
                    <button class="btn btn-danger btn-sm">删除</button>
                </td> -->
                <slot name="body" :row="obj"></slot>
            </tr>
        </tbody>
    </table>

</template>

<script>
export default {
    name: 'MyTable',
    props: {
        arr: Array
    }
}
</script>

<style scoped lang="less">
    .my-goods-list {
        .badge {
            margin-right: 5px;
            background-color: yellowgreen;
        }
    }

</style>