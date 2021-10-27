<template>
   <div class="card">
       <div class="card_title" v-html="title"></div>
       <div class="card_new_count" v-html="totalcasesCount"></div>
       <div class="card_desc" v-html="desc"></div>
   </div>
</template>

<script>
export default {
 props:['title', 'total_count','desc', 'new_count'],
  computed:{
    totalcasesCount:function() {
      return this.new_count.toString()
      .replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    }
  }
}
</script>