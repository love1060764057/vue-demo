<template>
    <div id="box">
        <!-- 导航栏 -->
        <div id="nav">
            <div id="nav-content">
                <div id="nav-content-1">
                <li v-for="item in items1">
                    <a href="">{{ item }}</a>
                </li>
                </div>
                <div id="nav-content-2">
                    <li v-for="item in items2">
                    <a href="">{{ item }}</a>
                </li>
                </div>
                <div id="nav-content-3">
                    <input type="text"/>
                    <span>
                        <a href="">中文</a>
                    </span>
                </div>
            </div>
            
        </div>

        <div id="content">
            <img src="../assets/toplog1.png" alt="">
            <div>
                <li v-for="item in items3">
                    <a href="" >{{ item }}</a>
                </li>
            </div>
        </div>
        <!-- 轮播图 -->
        <div id="bananer">
            <el-carousel :interval="5000" arrow="always" trigger="click">
            <el-carousel-item v-for="(item,index) in items4" :key="index"  >
            
            <img :src="item.url" />
            </el-carousel-item>
            </el-carousel>
        </div>
        <!-- 新闻 -->
        <div id="news">
            <div>
                <span class="color">头条新闻</span>
                <span>headline</span>
            </div>
            <div>
                <a href="" class="color">武大新闻网</a>
            </div>
        </div>
        <div id="news-content">
            <div id="news-content-1">
                <img :src="url1" alt="">
                <a href="" class="color a" :title="msg1">{{ msg1 }}</a>
                <span class="color" >{{ msg2 }}</span>
            </div>
            <div id="news-content-2">
                <div v-for="item in items5">
                    <div id="news-content-2-left" class="float-left">
                        <img :src="item.url" >
                    </div>
                    <div id="news-content-2-right" class="float-left">
                        <a href="" class="color a" :title="item.title">{{ item.title }}</a>
                        <span >{{ textSubstring(item.content) }}</span>
                    </div>
                </div>
                    
            </div>
            <div id="news-content-3">
                <div v-for="item in items6">
                    <div id="news-content-2-left" class="float-left">
                        <img :src="item.url" >
                    </div>
                    <div id="news-content-2-right" class="float-left">
                        <a href="" class="color a" :title="item.title">{{ item.title }}</a>
                        <span >{{ textSubstring(item.content) }}</span>
                    </div>
                </div>
                
            </div>
        </div>

        <div id="news-1">
            <div class="news-1-content">
                <div class="news-1-content-title">
                    <span>珞珈新闻</span>
                    <span>{{toUpperCase("news")}}</span>
                    <span class="float-right"><a href="" class="color a ">更多</a></span>
                </div>
                <div class="news-1-content-list">
                    <li class="float-left" v-for="item in items7">
                        <a href="" :title="item.title" class="color a">{{ item.title }}</a>
                    </li>
                    
                </div>
            </div>
            <div class="news-1-content">
                <div class="news-1-content-title">
                    <span>学术动态</span>
                    <span>{{toUpperCase("academic")}}</span>
                    <span class="float-right"><a href="" class="color a">更多</a></span>
                </div>
                <div class="news-1-content-list">
                    <li class="float-left" v-for="item in items8">
                        <a href="" :title="item.title" class="color a">{{ item.title }}</a>
                    </li>
                    
                </div>
            </div>
            <div class="news-1-content">
                <div class="news-1-content-title">
                    <span>珞珈新闻</span>
                    <span>{{toUpperCase("info")}}</span>
                    <span class="float-right"><a href="" class="color a">更多</a></span>
                </div>
                <div class="news-1-content-list">
                    <li class="float-left" v-for="item in items9">
                        <a href="" :title="item.title" class="color a">{{ item.title }}</a>
                    </li>
                    
                </div>
            </div>
        </div>


    </div>
  
</template>

<script setup lang="ts">
import { reactive,ref } from 'vue';
import { Search } from '@element-plus/icons-vue'

const items1 = reactive(["学生","教工","校友","考生","访客"]);
const items2 = reactive(["信息门户","邮箱系统","办公系统"]);
const items3 = reactive(["学校概况","机构设置","师资队伍","人才培养","科学研究","社会服务","交流合作","文化生活"]);
const items4 = reactive([
    {
        url:require("../assets/01.jpg")
    },
    {
        url:require("../assets/02.jpg")
    },
    {
        url:require("../assets/03.png")
    },
    {
        url:require("../assets/04.jpg")
    },

]);

const url1 = ref(require("../assets/news1.jpeg"));
const msg1 = ref("袁声军团队在《科学》杂志发表里德堡莫尔激子研究成果");
const msg2 = ref("​武汉大学为并列第一作者单位和通讯单位");

const items5 = reactive([
    {
        url:require("../assets/news2.jpeg"),
        title:"【顶天立地建学科】武汉大学学科建设委员会召开第二次全体会议",
        content:"新闻网讯（通讯员邢颖）6月28日下午，武汉大学学科建设委员会第二次全体会议在行政楼一会议室召开。会议由校长张平文主持。会议听取了武汉大学前沿交叉学科研究院筹建方案汇报并展开评议。各位委员就前沿交叉研究院的组织形式及运行机制、交叉学科人才培养模式、跨学科创新评价方式等方面进行了详细质询，重点围绕学校交叉学科发展顶层设计、政策制定与资源配置思路积极献言献策，并就加快我校学科交叉机制自主创新“特区”建设..."
    },
    {
        url:require("../assets/news3.jpg"),
        title:"武汉大学2023年本科招生宣传全面铺开（组图）",
        content:"翻越书山学海，共赴珞珈之约"
    },
    {
        url:require("../assets/news4.jpg"),
        title:"我校9项科技成果获高等学校科学研究优秀成果奖",
        content:"我校9项科技成果获高等学校科学研究优秀成果奖"
    },
]);

const items6 = reactive([
    {
        url:require("../assets/news5.jpg"),
        title:"【学习在线】习近平：不断深化对党的理论创新的规律性认识 在新时代新征程上取得更为丰硕的理论创新成果",
        content:"不断深化对党的理论创新的规律性认识 在新时代新征程上取得更为丰硕的理论创新成果"
    },
    {
        url:require("../assets/news6.jpg"),
        title:"《地球空间信息科学学报》（英文版）首次进入JCR Q1分区",
        content:"在全球遥感SCI期刊中排名第8"
    },
    {
        url:require("../assets/news7.jpeg"),
        title:"第三次院长联席会聚焦“精准育引学科领军人才，不断优化人才队伍结构”",
        content:"探讨“精准育引学科领军人才，不断优化人才队伍结构”"
    },
]);

const items7 = reactive([
    {
        title:"武大学子在中国机器人及人工智能大赛斩获2项国家一等奖"
    },
    {
        title:"【主题教育】周叶中讲授主题教育专题党课"
    },
    {
        title:"庆七一·“老少两代”同学同讲精神谱系活动圆满举办"
    },
    {
        title:"【记者调查】科技点亮校园生活"
    },
    {
        title:"爱的“大循环”，“山西校友号”校巴即将出发"
    },
    {
        title:"张平文会见巴黎西岱大学孔子学院院长一行"
    },
    {
        title:"学校举行大学生模拟政协提案大赛"
    },
    {
        title:"新华社湖北分社社长惠小勇受聘我校兼职教授"
    }
]);

const items8 = reactive([
    {
        title:"西南茶马古道文献资料整理与遗产保护研究学术研讨会召开"
    },
    {
        title:"【珞珈讲坛】陈晓红教授讲述经济学研究中的数学模型与方法"
    },
    {
        title:"刘天罡团队合作挖掘高能航空燃料分子倍半萜骨架"
    },
    {
        title:"【光明日报】黄惠康：新时代中国对外关系的基本法律遵循"
    },
    {
        title:"武汉大学／芝加哥大学联合培养博士后陈黎在Cell Research发表RNA甲基化测序新方法"
    },
    {
        title:"陈子林课题组在肿瘤荧光探针设计及其在成像和协同治疗方面取得新进展"
    },
    {
        title:"刘燕群关于妊娠期PM1暴露对母婴肠道菌群的影响研究取得新进展"
    },
    {
        title:"【人民日报】王增文：多措并举健全社会保障体系——助力共同富裕（新知新觉）"
    }
]);

const items9 = reactive([
    {
        title:"武汉大学130周年校庆公告"
    },
    {
        title:"关于2023年放暑假及做好暑期相关工作的通知"
    },
    {
        title:"关于2023年暑假期间学校管理运行、服务保障、公共资源开放的通知"
    },
    {
        title:"关于第十八届“挑战杯”全国大学生课外学术科技作品竞赛拟推报作品的公示"
    },
    {
        title:"武汉大学幼儿园2023年秋季招生公告"
    },
    {
        title:"关于集中征集武汉大学历届毕业生合影照片的通知"
    },
    {
        title:"800M高场固体核磁共振波谱仪试运行公告"
    },
    {
        title:"新华社湖北分社社长惠小勇受聘我校兼职教授"
    }
]);



const textSubstring = (value:string)=>{
    return value.substring(0,30);
}

const toUpperCase = (value:string)=>{
    return value.toUpperCase();
}

</script>

<style lang="scss">
// 清空默认样式
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

#box{
    width: 100%;
    height: 100%;
}


// 导航栏样式
#nav{
    position: relative;
    width: 100%;
    height: 60px;
    background-image: url("../assets/bg.png");
}
#nav-content{
    position: relative;
    width: 70%;
    height: 60px;
    left: 15%;
}
#nav-content-1{
    position: relative;
    display: inline-block;
    width: 20%;
    height: 60px;
    
    
}
#nav-content li{
    width: 19%;
}
#nav-content li,#content li{
    position: relative;
    top: 15px;
    float: left;
    text-align: center;
    list-style: none;
    height: 30px;
    line-height: 30px;
    margin-left: 1%;
}

li{
    list-style: none;
}
a{
    text-decoration: none;
    color: white;;
}
#nav-content-2{
    position: relative;
    display: inline-block;
    width: 30%;
    height: 60px;

}
#nav-content-3{
    position: relative;
    display: inline-block;
    width: 50%;
    height: 60px;
}

#nav-content-3>input,#nav-content-3>span{
    position: absolute;
    height: 30px;
    top: 15px;
    line-height: 30px;
}

#nav-content-3>input{
    width: 30%;
    border-radius: 5px;
    border: 0;
    right:20% ;
}
#nav-content-3>span{
    width: 20%;
    right: 0;
    text-align: center;
}

#content{
    position: relative;
    width: 70%;
    left: 15%;
    height: 100px;
}

#content>img{
    display: inline-block;
    width: 20%;
    height: 78px;
    margin-bottom: 11px;
}
#content>div{
    display: inline-block;
    width: 80%;
    height: 100px;
}
#content>div>li{
    position: relative;
    top: 20px;
    height: 60px;
    width: 10%;
}
#content>div>li:nth-child(1){
    margin-left: 10%;
}
#content>div>li>a{
    height: 60px;
    color: black;
    line-height: 60px;
    display: inline-block;
}

// 轮播图样式
#bananer{
    position: relative;
    left: 15%;
    width: 70%;
    height: 300px;
}

.el-carousel__item h3 {
  color: #475669;
  opacity: 0.75;
  line-height: 300px;
  margin: 0;
  text-align: center;
}

.el-carousel__item >img{
  width: 100%;
  height: 100%;
}
// 新闻
#news{
    position: relative;
    width: 70%;
    height: 60px;
    left: 15%;
}
#news>div{
    width: 50%;
    height: 100%;
    display: inline-block;
}
#news>div>a{
    height: 40px;
    margin-top: 10px;
    color: black;
    position: absolute;
    line-height: 40px;
    right: 10px;
}
#news>div>span{
    position: relative;
    display: inline;
    float: left;
    height: 40px;
    line-height: 40px;
    color: black;
    margin-top: 10px;
}
#news>div>span:nth-child(2){
    margin-left: 10px;
}

#news-content{
    width: 70%;
    height: 360px;
    display: flex;
    position: relative;
    left: 15%;
}
#news-content-1,#news-content-2,#news-content-3{
    flex: 1;
    width: 0;
    margin-right: 10px;
    border-top: 2px solid #1ca132;
}
#news-content-3{
    margin-right: 0;
}
#news-content-1>img{
    width: 100%;
    height: 300px;
}
.color{
    color: black;
}
#news-content-1>a{
    display: inline-block;
    width: 90%;
    margin-left: 5%;
}
.a{
    display: inline-block;
    white-space:nowrap;
    overflow:hidden;
    text-overflow:ellipsis; 
}
.a:hover{
    color: #1ca132;
}
#news-content-1>span{
    width: 90%;
    display: inline-block;
    height: 20px;
    line-height: 20px;
    font-size: 13px;
    margin-left: 5%;
}
#news-content-2>div,#news-content-3>div{
    width: 90%;
    height: 120px;
    margin: 0 5%;
}
#news-content-2-left{
    display: inline-block;
    width: 35%;
    height: 100px;
    margin-right: 10%;
    margin-top: 10px;
}
#news-content-2-left>img{
    display: inline-block;
    width: 100%;
    height: 100%;
}
.float-left{
    float: left;
}
#news-content-2-right{
    display: inline-block;
    width: 55%;
    height: 100px;
    margin-top: 10px;
}
#news-content-2-right>a,#news-content-2-right>span{
    display: inline-block;
    width: 90%;
    overflow: hidden;
}
#news-content-2-right>a{
    height: 20px;
}
#news-content-2-right>span{
    height: 80px;
}
#news-1{
    display: flex;
    width:70%;
    position: relative;
    left: 15%;
    height: 380px;
}
.news-1-content{
    flex: 1;
    width: 0;
    height: 300px;
}
.news-1-content-title{
    width: 90%;
    height: 60px;
    margin-left: 5px;
}
.news-1-content-title>span{
    display: inline-block;
    height: 40px;
    line-height: 40px;
    margin-top: 10px;
    margin-right: 10px;
    font-size: 18px;
}
.news-1-content-title>span:nth-child(2){
    font-size: 15px;
}
.float-right{
    float: right;
}
.news-1-content-list{
    width: 90%;
    height: 240x;
    margin-left: 5px;
}
.news-1-content-list>li{
    width: 100%;
    height: 30px;
    line-height: 40px;
    margin: 0;
}
.news-1-content-list>li>a{
    width: 100%;
    height: 30;
    line-height: 30px;
}
</style>
