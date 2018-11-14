<template>
<div id="app">
    <div class="flex">
        <div>
            <calendar :range="calendar2.range" :lunar="calendar2.lunar" :value="calendar2.value" :begin="calendar2.begin" :end="calendar2.end" @select="calendar2.select"></calendar>
        </div>
    </div>
</div>
</template>

<script>
 
import calendar from './calendar.vue'

export default {
    name: 'app',
    components: {
        calendar
    },
    data(){
        return {
            calendar2:{
                range:true,
                //value:[[2017,12,1],[2019,2,16]], //默认日期
                lunar:false, //显示农历
                begin:[1999,1,1], //可选开始日期
                //end:[,12,16], //可选结束日期
                select(begin,end){
									console.log(`开始时间:${begin[0]}-${begin[1]+1}-${begin[2]}\n结束时间:${end[0]}-${end[1]+1}-${end[2]}`);
                }
            },
        }
    },
    methods:{}
}
</script>

<style>
/*demo*/
body,div{margin:0;padding:0}
.flex{
    box-sizing: border-box;

    display: -webkit-box;
    -webkit-box-pack: start;
    -webkit-box-align: start;

    display: -webkit-flex;
    -webkit-justify-content: space-between;
    -webkit-align-items: top;

    display: flex;
    justify-content: space-between;
    align-items: top;
    flex-flow:row wrap
}
.flex>div{
   /* margin:10px; */
    padding:20px 0;
    width:100%;
    /* min-width:300px; */
    /* border: 1px solid #ccc; */
    border-radius: 2px;
    position: relative;
}
.flex>div>span{
    position: absolute;
    left:0px;
    top:0px;
    padding:5px 10px;
    font-family: "PingFang SC","Hiragino Sans GB","STHeiti","Microsoft YaHei","WenQuanYi Micro Hei",sans-serif;
    font-size:10px;
    border-radius:0 0 2px 0;
    background:#ea6151;
    color:#fff;
}
</style>
