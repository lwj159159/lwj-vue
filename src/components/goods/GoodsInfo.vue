<template>
  <div class="goodsinfo-container">

    <!-- 商品轮播图 -->
    <div class="mui-card">
				<div class="mui-card-content">
					<div class="mui-card-content-inner">
						这是一个最简单的卡片视图控件；卡片视图常用来显示完整独立的一段信息，比如一篇文章的预览图、作者信息、点赞数量等
					</div>
				</div>
		</div>

      <!-- 商品购买区域 -->
    <div class="mui-card">
      <div class="mui-card-header">页眉</div>
      <div class="mui-card-content">
        <div class="mui-card-content-inner">
          包含页眉页脚的卡片，页眉常用来显示面板标题，页脚用来显示额外信息或支持的操作（比如点赞、评论等）
        </div>
      </div>
      <div class="mui-card-footer">页脚</div>
    </div>
      <!-- 商品参数区域 -->
    <div class="mui-card">
      <div class="mui-card-header">页眉</div>
      <div class="mui-card-content">
        <div class="mui-card-content-inner">
          包含页眉页脚的卡片，页眉常用来显示面板标题，页脚用来显示额外信息或支持的操作（比如点赞、评论等）
        </div>
      </div>
      <div class="mui-card-footer">页脚</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: this.$route.params.id, //
      goodsinfo: {} //获取到商品的信息
    };
  },
  methods: {
    getLunbotu() {
      this.$http.get("api/getthumimages/" + this.id).then(result => {
        if(result.body.status === 0){
          // 先循环轮播图数组的每一项,为item添加img属性,因为轮播图组件中,只认识item.img,不认识item.src

        }
      })
    },
    getGoodsInfo() {
      // 获取商品的信息
      this.$http.get("api/goods/getinfo/" + this.id).then(result => {
        if (result.body.status === 0) {
          this.goodsinfo = result.body.message[0];
        }
      });
    },
   
  }
};
</script>

<style lang="scss" scoped>
.goodsinfo-container {
  background-color: #eee;
  overflow: hidden;
}
</style>

