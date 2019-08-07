<template>
    <div class="main-content">
        <div class="index-main">
            <img src="../assets/background.png" alt="背景图片" id="index-image" class="index-image">
            <div class="bg"></div>
            <div class="index-mid-box">
                <form class="J-search-form">
                    <div class="float-mid">
                        <p class="en-world">If not now, when?</p>
                        <p class="en-world">If not me, who?</p>
                        <p class="ch-world">此时此刻，非我莫属！</p>
                        <div class="search-box">
                            <span @click="noShow" class="search-topic" id="search-topic">请输入职位关键词</span>
                            <div class="search-bg"></div>
                            <input id="search-text" type="text" class="search-text" @focus="noShow" @blur="show" @input="noShow" maxlength="30" v-model="inputContent">
                            <input type="submit" class="search-btn" value="搜索">
                        </div>
                        <div class="hot-text">
                            热门搜索：
                            <a v-for="item in searchKeys" :href="item.url" class="search-key" :key="item.id">{{item.name}}</a>
                        </div>
                    </div>
                </form>
            </div>
        </div>
        <div class="newPosition">
            <div class="newPosition-content">
                <div class="newPosition-list">
                    <div class="more-position">
                        最新职位
                        <a class="more" href="MorePosition">更多</a>
                    </div>
                    <ul class="position-list" :style="{top: top}" @mouseenter="Stop" @mouseleave="Up">
                        <li v-for="position in newPositions" :key="position.id" class="scroll-4">
                            <a  :href="position.url" class="position">{{position.position}}</a>
                            <em class="time">3分钟前</em>
                            <em class="city" title="杭州">杭州</em>
                        </li>
                    </ul>
                </div>
                <aside class="aside">
                    <a href="https://www.aliyun.com/careers?spm=a2obv.11410899.0.aliyun.55ef6c61J1Ym2H" class="show-pic pic-1">
                        <img src="../assets/aside-1.png" alt="阿里云">
                    </a>
                    <a href="https://job.alibaba.com/zhaopin/informationPlatformBu.htm?" class="show-pic pic-2">
                        <img src="../assets/aside-2.svg" alt="合作企业">
                    </a>
                </aside>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'main-content',
        data() {
            return {
                searchKeys: [
                    {id: 0, name: 'JAVA', url: 'javascript:void()'},
                    {id: 1, name: 'IOS', url: 'javascript:void()'},
                    {id: 2, name: '数据', url: 'javascript:void()'},
                    {id: 3, name: '安全', url: 'javascript:void()'},
                    {id: 4, name: '搜索', url: 'javascript:void()'},
                    {id: 5, name: '算法', url: 'javascript:void()'},
                    {id: 6, name: '运营', url: 'javascript:void()'},
                    {id: 7, name: '视觉', url: 'javascript:void()'},
                    {id: 8, name: '交互', url: 'javascript:void()'},
                    {id: 9, name: '前端', url: 'javascript:void()'}
                ],
                newPositions: [
                    {
                        id: 10,
                        position: '阿里云智能事业群-智能场景方案架构师-GTS',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 11,
                        position: '商业智能部-资深数据分析专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 12,
                        position: '天猫消费者平台产品中心-会员产品经理--杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 13,
                        position: 'AliExpress-会员产品专家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 14,
                        position: '商业智能部-数据分析专家（决策支持）-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 15,
                        position: '天猫市场部-媒介运营专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 16,
                        position: '集团法务部-高端岗位（运营法务）-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 17,
                        position: '天猫用研-高级行业及市场策略研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 18,
                        position: '商业智能部-数据分析专家/高级专家-北京',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 19,
                        position: '商业智能部-数据分析专家/高级专家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 20,
                        position: '天猫品牌营销中心-品牌营销高级专家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 21,
                        position: '阿里汽车-摩托车-行业运营专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 22,
                        position: '蚂蚁金服-经济学家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 23,
                        position: '新零售研究中心-新零售市场研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 24,
                        position: '新零售研究中心-高级商品管理研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 25,
                        position: '集团法务部-法律专家（B2B）-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 26,
                        position: '阿里云智能事业群-智能场景方案架构师-GTS',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 27,
                        position: '商业智能部-资深数据分析专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 28,
                        position: '天猫消费者平台产品中心-会员产品经理--杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 29,
                        position: 'AliExpress-会员产品专家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 30,
                        position: '商业智能部-数据分析专家（决策支持）-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 31,
                        position: '天猫市场部-媒介运营专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 32,
                        position: '集团法务部-高端岗位（运营法务）-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 33,
                        position: '天猫用研-高级行业及市场策略研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 34,
                        position: '商业智能部-数据分析专家/高级专家-北京',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 35,
                        position: '商业智能部-数据分析专家/高级专家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 36,
                        position: '天猫品牌营销中心-品牌营销高级专家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id:37,
                        position: '阿里汽车-摩托车-行业运营专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 38,
                        position: '蚂蚁金服-经济学家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 39,
                        position: '新零售研究中心-新零售市场研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 40,
                        position: '新零售研究中心-高级商品管理研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 41,
                        position: '集团法务部-法律专家（B2B）-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id:42,
                        position: '阿里汽车-摩托车-行业运营专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 43,
                        position: '蚂蚁金服-经济学家',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 44,
                        position: '新零售研究中心-新零售市场研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 45,
                        position: '新零售研究中心-高级商品管理研究专家-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    },
                    {
                        id: 46,
                        position: '集团法务部-法律专家（B2B）-杭州',
                        url: 'https://job.alibaba.com/zhaopin/PositionDetail.htm?positionCode=GP555105'
                    }
                ],
                activeIndex: 0,
                intNum: undefined,
                inputContent: ''
            }
        },
        computed: {
            // 获取滚动的高度
            top() {
                return -this.activeIndex * 5 + 'px';
            }
        },
        created() {
            this.ScrollUp();
        },
        methods: {
            // 职位信息滚动
            ScrollUp(){
                this.intNum = setInterval(() => {
                    if(this.activeIndex < this.newPositions.length*9) {
                        this.activeIndex += 1;
                    } else {
                        this.activeIndex = 0;
                    }
                }, 200);
            },
            // 当鼠标悬停时停止滚动
            Stop(){
                clearInterval(this.intNum);
            },
            // 当鼠标离开时继续滚动
            Up(){
                this.ScrollUp();
            },
            // 搜索框被点击时清空搜索内容
            show() {
                if (this.inputContent === '') {
                    let span = document.getElementById('search-topic');
                    span.style.display = 'block';
                    span.style.zIndex = 90;
                }

            },
            // 搜索框 blur 时显示默认搜索
            noShow() {
                let span = document.getElementById('search-topic');
                let input = document.getElementById('search-text');
                span.style.display = 'none';
                span.style.zIndex = 0;
                input.focus();
            }
        }
    }
</script>

<style scoped>
.index-main {
    position: relative;
    height: 478px;
    overflow: hidden;
}

.index-main,
.J-search-form,
.index-main .bg {
    width: 100%;
}

.index-main .index-image {
    vertical-align: middle;
    width: 1440px;
    height: 478px;
}

.index-main .bg {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    background: rgba(31, 56, 88, .4);
}

/*=========title和搜素部分=========*/
.index-mid-box {
    height: 100%;
    width: 1000px;
    position: absolute;
    margin-left: -500px;
    top: 0;
    left: 50%;
}

.index-mid-box .float-mid {
    position: absolute;
    left: 50%;
    top: 50%;
    margin-left: -245px;
    margin-top: -145px;
}

.float-mid .en-world {
    font-size: 54px;
    color: #fff;
    line-height: 56px;
    font-weight: 500;
    font-family: Rufina-Regular;
}

.float-mid .ch-world {
    margin-bottom: 38px;
    line-height: 48px;
    font-size: 34px;
    font-weight: 600;
    font-family: PingFang-Thin;
}

.float-mid .search-box {
    width: 490px;
    height: 60px;
    position: relative;
    margin: 0 auto;
    top: 0;
    padding: 0;
}

.float-mid .search-topic {
    position: absolute;
    z-index: 90;
    font-size: 14px;
    left: 15px;
    top: 50%;
    display: block;
    width: 300px;
    color: rgba(31,56,88,.3);
    line-height: 20px;
    margin-top: -10px;
    margin-left: 8px;
}

.float-mid .search-bg {
    width: 100%;
    height: 100%;
    background: #fff;
    position: absolute;
    opacity: .1;
}

.float-mid .search-text {
    width: 368px;
    height: 40px;
    margin-top: 6px;
    margin-left: 10px;
    box-sizing: border-box;
    border-radius: 3px;
    padding: 10px 0 8px;
    text-indent: 10px;
    float: left;
    border: 0;
    z-index: 80;
    font-size: 14px;
    position: relative;
    top: 4px;
    outline: none;
}

.float-mid .search-btn {
    width: 92px;
    height: 40px;
    border-radius: 3px;
    margin-top: 10px;
    margin-left: 10px;
    position: relative;
    z-index: 2;
    background: #F37327;
    font-size: 14px;
    color: #fff;
    display: inline-block;
    text-align: center;
    cursor: pointer;
    border: 0;
    box-sizing: border-box;
}


.float-mid .hot-text {
    text-align: center;
    padding: 10px 0;
}

.hot-text,
.hot-text a {
    color: rgba(255, 255, 255, .8);
}

.hot-text a {
    padding-right: 14px;
}

.hot-text a:hover {
    color: #F37327;
}

/*=========职位信息=========*/
.newPosition {
    width: 100%;
    overflow: hidden;
}

.newPosition-content {
    width: 1180px;
    height: 300px;
    margin: 32px auto;
}

.newPosition-list,
.aside .show-pic {
    background: #FFFFFF;
    box-shadow: 0 0 15px 0 rgba(31, 56, 88, .08);
    border-radius: 3px;
}

.newPosition-list {
    width: 850px;
    height: 300px;
    float: left;
    overflow: hidden;
    position: relative;
}

.more-position {
    height: 49px;
    border-bottom: 1px solid rgba(31, 56, 88, .06);
    line-height: 49px;
    background: white;
    font-size: 14px;
    padding: 0 14px;
    color: #000;
    position: relative;
    z-index: 2;
}

.more-position .more {
    float: right;
    font-size: 14px;
    color: rgba(31, 56, 88, .6);
    cursor: pointer;
    text-decoration: none;
}

.position-list {
    position: relative;
    transition: top 0.5s;
}

.position-list li {
    overflow: hidden;
    padding: 0 14px;
    line-height: 50px;
    font-size: 14px;
}

.position-list .position {
    float: left;
    color: #3C99D8;
    cursor: pointer;
    width: 400px;
    overflow: hidden;
    -ms-text-overflow: ellipsis;
    text-overflow: ellipsis;
    white-space: nowrap;
}

.position-list .time {
    float: right;
    font-style: normal;
    text-align: right;
    color: rgba(31, 56, 88, .6);
}

.position-list .city {
    float: right;
    font-style: normal;
    color: rgba(0, 0, 0, .6);
    margin-right: 70px;
    width: 202px;
    overflow: hidden;
    -ms-text-overflow: ellipsis;
    text-overflow: ellipsis;
    white-space: nowrap;
}

.aside {
    float: right;
    width: 310px;
}

.aside .show-pic {
    display: block;
    cursor: pointer;
    height: 140px;
    text-align: center;
    line-height: 140px;
}

.show-pic.pic-1  {
    margin-bottom: 20px;
}
</style>
