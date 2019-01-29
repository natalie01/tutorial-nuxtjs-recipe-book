<template>
    <section class = "single-recipe">
        <h1>Title {{ recipe.title }}</h1>
        <div>
            <img class = "recipe-image" :src ="recipe.thumbnail" alt = "">
        </div>
        <p>{{ recipe.previewText }}</p>
        <p>{{ recipe.descriptionText }}</p>
    </section>
</template>

<script>
export default {
    asyncData( context ){
        return new Promise((resolve,reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
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

                    ].find( el => el.id === context.params.id)
                })
            },1500)
        })
    }
}
</script>

<style scoped>
.single-recipe{
    display:flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}

.recipe-image{
    width:100%;
}
</style>