<template>  
    <div class="card" :class="slideWidth">
        <div class="card__header">
            <img :src="cardImg" :alt="recipe.Title" class="card__img">
            <div class="card__overlay">
                <div class="topleft" v-if="slideWidth === 'medium' || slideWidth === 'large'">
                </div>
                <div class="topright">
                </div>
                <div class="recipe-attributes">
                    <div class="recipe-attributes__left">
                        <p class="recipe-attributes__left__difficulty" >{{ recipe.Difficulty }} <span class="emoji"></span> </p>
                        <p class="recipe-attributes__left__ingredients">13 ingredients</p>
                    </div>
                    <div class="recipe-attributes__right">
                        <p class="recipe-attributes__rightcook-time">&#128336; {{ recipe.Cooktime }}min</p>
                    </div>
                </div>                
            </div>
        </div>        
        <div class="card__title">
            <h4 class="card-headline">{{ recipe.Title }}</h4>
            <div class="card__body">
                      
                <router-link :to="{ name: 'RecipeDetails', params: { id: recipe.id} }" v-if="slideWidth === 'medium' || slideWidth === 'large'">
                    <button class="button button--green">Cook <i class="icofont-arrow-right"></i></button>
                </router-link>
            </div>
            <div class="card__gallery" v-if="slideWidth === 'full' ">
                
            </div>            
        </div>
    </div>
  
 
</template>

<script>


export default {
    props: [ 'recipe', 'cardSize', 'slideWidth' ],
    components: {  },
    data(){
        return{     
            cardImg: '/mfd-team2/img/food/placeholder.png',
            emoji: '&#128336;'
        }
    },
    mounted(){
        if(this.recipe.ImageURL)
        {
            this.cardImg = require('../../../public/img/food/'+this.recipe.ImageURL)
        }
    }
}
</script> 

<style lang="scss">



</style>