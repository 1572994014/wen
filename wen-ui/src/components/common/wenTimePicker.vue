<style scoped>
    .controller{
        position: relative;
        width: 180px;
        border: 1px solid #dcdfe6;
        display: inline-flex;
        border-radius: 4px;
        background-color: #FFFFFF;
        box-sizing: border-box;
    }
    .controller::before{
        margin-top: -15px;
        margin-left: 12%;
        margin-right: 12%;
        padding-left: 50%;
        top: 50%;
        left: 0;
        right: 0;
        position: absolute;
        content: "";
        display: block;
        height: 32px;
        /* transform: translateY(-50%); */
        border-top: 1px solid #e4e7ed;
        border-bottom: 1px solid #e4e7ed;
        box-sizing: border-box;
    }
    .controller>div{
        width: 100%;
        white-space: nowrap;
    }
    .controller>div>div{
        width: 33%;
        white-space: nowrap;
        overflow: hidden;
        position: relative;
        display: inline-block;
    }
    .wrap{
        position: relative;
        width: 100%;
        max-height: 190px;
        overflow:hidden;
        display: inline-block;
        vertical-align: top;
        white-space: nowrap;
    }
    .wrap>ul{
        height: 100%;
        max-height: inherit;
        margin-bottom: -17px;
        margin-right: -17px;
        padding-bottom: 15px;
        overflow: scroll;
    }
    .wrap>ul::before, .wrap>ul::after{
        content: "";
        display: block;
        height: 80px;
    }
    .wrap>ul>li{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 32px;
    }
</style>
<template>
    <div class="controller">
        <div>
            <div>
                <div class="wrap">
                    <ul>
                        <li v-for="i in 10" :key="i">{{i}}</li>
                    </ul>
                </div>
            </div>
            <div>
                <div class="wrap">
                    <ul>
                        <li v-for="i in 10" :key="i">{{i + 10}}</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>
