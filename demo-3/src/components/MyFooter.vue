<template>
    <div class="my-footer">
        <div class="custom-control custom-checkbox">
            <input type="checkbox" id="footerCheck" class="custom-control-input" v-model="isAll">
            <label for="footerCheck" class="custom-control-label">全选</label>
        </div>
        <div>
            <span>合计：</span>
            <span class="price">hkd {{allPrice}} </span>
        </div>
        <button class="footer-btn btn btn-primary" type="button">结算 （{{allCount}}）</button>
    </div>
</template>

<script>
export default {
    props: {
        arr: Array
    },
    computed: {
        isAll: {
            set(vel) {
                this.$emit('changeAll', val)
            },
            get() {
                return this.arr.every(obj => obj.goods_state === true)
            }
        },
        allCount() {
            return this.arr.reduce((sum, obj) => {
                if(obj.goods_state === true) {
                    sum += obj.goods_count
                }
                return sum
            }, 0)
        },
        allPrice() {
            return this.arr.reduce((sum, obj) => {
                if (obj.goods_state) {
                    sum += obj.goods_count * obj.goods_price
                }
                return sum;
            }, 0)
        }
    }
}
</script>

<style lang="less" scoped>
.my-footer {
    position: fixed;
    z-index:2;
    bottom: 0;
    width: 100%;
    height: 50px;
    border-top: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 10px;
    background: #fff;
    .price {
        color: red;
        font-weight: bold;
        font-size: 15px;
    }
    .footer-btn {
        min-width: 80px;
        height: 30px;
        line-height: 30px;
        border-radius: 25px;
        padding: 0;
        font-size: 12px;
    }
}

</style>