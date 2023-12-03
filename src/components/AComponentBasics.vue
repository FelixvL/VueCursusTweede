<script setup>
    import { ref } from 'vue'
    import AAButtonCounter from './AAButtonCounter.vue';
    import AABBlogPost from './AABBlogPost.vue';
    import AACBlogPostLoop from './AACBlogPostLoop.vue';
    import AADBlogPostEmit from './AADBlogPostEmit.vue';
    import AAEBlogPostSlot from './AAEBlogPostSlot.vue';
    const a = 3
    const posts = ref([
  { id: 1, title: 'My journey with Vue' },
  { id: 2, title: 'Blogging with Vue' },
  { id: 3, title: 'Why Vue is so fun' }
])
    const postFontSize = ref(1)
    function smaller(){
        postFontSize.value -= 0.1
    }
    function doen(){
        console.log("deze is geemit, deze log is in parent");
    }
</script>
<template>
    <div>
        A: {{ a }}
        <AAButtonCounter/>
        <AAButtonCounter/>
        <AAButtonCounter/>
        <AABBlogPost titel="De Eerste" />
        <AABBlogPost titel="De Tweede" />
        <AABBlogPost titel="De Derde" />
        <AACBlogPostLoop 
            v-for="post in posts"
            :key="post.id"
            :titel="post.title"  
        />
        <div :style="{fontSize:postFontSize + 'em'}">
            <AADBlogPostEmit titel="Go" @enlarge-text="postFontSize += 0.1" @ensmall-text="smaller()" @derdeemit="doen()"/>        
            Tekst In Div Boven Emit Component
        </div>
        <AAEBlogPostSlot>
            Dit is innerHTML bij de eerste
        </AAEBlogPostSlot>
        <AAEBlogPostSlot>
            Bij de tweede is dit de innerHTML
        </AAEBlogPostSlot>
    </div>
</template>