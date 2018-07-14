<style scoped>
  .layout{
    width: 100%;
    min-height: 100vh;
  }
  .margin10{
    margin: 10px 0 40px;
  }
  .blog-main{
    width: 95%;
    min-height: 100vh;
    -moz-box-shadow: 0px 19px 30px #888888; /* 老的 Firefox */
    box-shadow: 0px 19px 30px #888888;
    margin: auto;
    overflow: hidden;
  }
  .float-left{
    float:left;
  }
  .my-detail{
    -moz-box-shadow: 0px 0px 30px #d8d8d8; /* 老的 Firefox */
    box-shadow: 0px 0px 30px #d8d8d8;
    width: 30%;
    min-height: 100vh;

  }
  .contain{
    width: 70%;
    padding: 0 20px;
  }
  .me-photo{
    min-width: 100px;
    height: auto;
    width: 50%;
    border-radius:50%;
    margin: 30px 0;
  }
  .hand{
    cursor:pointer
  }
  .sm-title{
    font-size: 1.8rem;
  }
  .detail-box{
    border-bottom: 1px solid #ccc;
  }
  .comment-title{
    text-align: left;
    padding: 20px;
    font-size: 1.5rem;

  }
  .comment-detail,.article-detail{
    font-weight: lighter;
    font-size: 1.3rem;
    color: #2d8cf0;
    text-align: left;
    overflow:hidden;
    text-overflow:ellipsis;
    display:-webkit-box;
    -webkit-box-orient:vertical;
    -webkit-line-clamp:2;
    margin: 15px 10px;
    letter-spacing: 2px;
  }
  .detail-em{
    font-size: 1rem;
  }
  .essay-main,.article-main{
    padding: 0px 10px;
    font-size: 13px;
    line-height: 23px;
    text-align: left;
  }
  .comment-more{
    text-align: right;
    font-size: 1.3rem;
    margin: 40px 0 10px;
    padding: 20px;
  }
 .article-detail{
    font-size: 1.6rem;
  }
  .article-main{
    font-size: 1.2rem;
  }
  .essay-footer{
    margin: 10px 20px 30px;
    text-align: right;
  }
  .clearOverFlat{
    overflow: hidden;
    border-bottom: 1px solid #ccc;
    padding: 30px 0;
  }
  .left{
    float: left;
  }
  .data-left{
    width: 20%;
  }
  .data-right{
    width: 79%;
  }
  .specitalFont{
    font-family: Playfair Display;
    font-style: italic;
    color: #999;
    height: 126px;
    font-size: 1.8rem;
    margin-top: 20px;
  }
  .clo-2{
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    letter-spacing: 2px;
  }
  .more{
    color: #2d8cf0;
    position: absolute;
    right: 5.5%;;
    margin-top: 10px;
  }
  .second-detail{
    padding: 0 10px;
    text-align: left;
  }
  .second-detail-span{
    display:inline-block;
    margin-right: 30px;
  }


</style>
<template>
  <div class="layout">
    <div class="blog-main">
        <div class="my-detail float-left">
          <div class="detail-box">
            <img class="me-photo" src="static/blog/me.jpg" alt="我">
            <h1 class="sm-title hand">吴思敏</h1>
            <div class="margin10">
              <h1>Web开发工程师</h1>
              <ul>
                <li>微信：Simin5Wu</li>
              </ul>
            </div>
          </div>
          <div class="comments">
            <h1 class="comment-title">最新评论</h1>
            <div class="comment-main">
              <ul v-for="(item,index) in commentList">
                <li>
                  <div class="essay-title hand" @click="commentopen">
                    <h1 class="comment-detail" ><em class="detail-em">{{index+1}}</em>{{item.articleTitle}}</h1>
                 </div>
                  <div class="essay-main">{{item.comment}}</div>
                  <div class="essay-footer">
                      <p>--{{item.peopleName}}</p>
                      <p>{{item.commentTime}}</p>
                  </div>
                </li>
              </ul>
              <div class="comment-more hand">...更多</div>
            </div>
          </div>
        </div>
        <div class="contain float-left">
          <ul  v-for="(item,index) in articleList">
            <li class="clearOverFlat">
              <div class="specitalFont left data-left">
                <div>
                  <div>{{item.postMonth}}</div>
                  <span>{{item.postDay}}</span>
                  <p><em>/</em>{{item.postYear}}</p>
                </div>
              </div>
              <div class="left data-right">
                <h1 class="article-detail hand" @click="openArtical" ><em class="detail-em">{{index+1}}</em>{{item.articleTitle}}</h1>
                <h2 class="second-detail"><span class="second-detail-span">作者：{{item.author}}</span> <span class="second-detail-span">星期：{{item.week}}</span> <span class="second-detail-span">评论数：{{item.commentnum}}</span></h2>
                <p class="article-main clo-2" >{{item.articleMain}} </p><span class="more hand" @click="openArtical">阅读全文</span>
              </div>
            </li>
          </ul>
        </div>
    </div>
  </div>
</template>
<script>
  export default {
      name:"Blog",
      data () {
      return {
          commentList:[{
            articleTitle:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快",
            comment:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将",
            peopleName:"吴思敏",
            commentTime:"2017-01-01 10:01:01"
          },{
            articleTitle:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快",
            comment:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将",
            peopleName:"吴思敏",
            commentTime:"2017-01-01 10:01:01"
          },{
            articleTitle:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快",
            comment:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将",
            peopleName:"吴思敏",
            commentTime:"2017-01-01 10:01:01"
          },{
            articleTitle:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快",
            comment:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将",
            peopleName:"吴思敏",
            commentTime:"2017-01-01 10:01:01"
          }
          ],
          articleList:[
            {
              articleTitle:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快",
              articleMain:"虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快将虎骨呼唤你今年空间看好几遍尽快尽快尽快可尽快尽快",
              author:"wusimin",
              postTime:"2017-07-01 10:01:01",
              postMonth:"July",
              postDay:"01",
              postYear:"2017",
              commentnum:"2",
              week:"Thursday"
            }
          ]
      };
    },
    methods: {
      openArtical(){
        this.$router.push({ path: "/commentPost"})
      },
      commentopen(){
        this.$router.push({ path: "/commentList"})
      }

  }
}
</script>
