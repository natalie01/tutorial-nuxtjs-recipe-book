<template>
    <div>
    <h1>Recipes</h1>
    <section class = 'recipes'>
        <Recipe v-for = 'recipe in recipes' 
        :key = 'recipe.id' 
        :thumbnail = 'recipe.thumbnail' 
        :title = 'recipe.title'
        :previewText = 'recipe.previewText'
        :id = 'recipe.id' />
    </section>
    <div>
        Icons made by <a href="https://www.freepik.com/" title="Freepik">Freepik</a> from <a href="https://www.flaticon.es/" 			    title="Flaticon">www.flaticon.com</a> is licensed by <a href="http://creativecommons.org/licenses/by/3.0/" 			    title="Creative Commons BY 3.0" target="_blank">CC 3.0 BY</a>
    </div>
   </div>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
    components:{
        Recipe
    },
    asyncData( ){
        return new Promise((resolve,reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id : "1",
                            title : "Dornish Wine",
                            previewText : "Delicious Wine!",
                            descriptionText : 'description here',
                            thumbnail: "https://image.flaticon.com/icons/svg/1200/1200973.svg"
                        },
                                                {
                            id : "2",
                            title : "Dornish Wine",
                            previewText : "Delicious Wine!",
                            descriptionText : 'description here',
                            thumbnail: "https://image.flaticon.com/icons/svg/1200/1200973.svg"
                        }

                    ]
                })
            },1500)
        })
    }
}
</script>


<style scoped>
.recipes {
 display:flex;
 flex-flow :row wrap;   
 justify-content: center;
 align-items: center;
}

</style>