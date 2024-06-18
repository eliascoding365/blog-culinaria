<script>
    import PostBlog from './PostBlog.vue';
    import imagem1 from '../assets/download.jpg'
    import imagem2 from '../assets/download2.jpg'

    export default{
        data() {
            return {
                imagem1: imagem1,
                imagem2: imagem2,
            }
        },
        components: {
            PostBlog,
        }
    }
</script>

<template>
    <div class='post'>
        <PostBlog 
            title="Strogonorf"
            text="Em português, Estrogonofe é um prato originário da Rússia, mas que se tornou popular em muitos países, incluindo o Brasil. É feito com tiras de carne, geralmente de filé mignon, e cogumelos, cozidos em uma panela com molho à base de creme de leite e mostarda. O prato é geralmente servido com arroz ou batatas cozidas. O Estrogonofe é uma opção deliciosa para jantares e almoços, e pode ser encontrado em muitos restaurantes brasileiros."
            :imagem="imagem1"
        />
        <PostBlog 
            title="Tiramisu"
            text="Tiramisu, uma sobremesa italiana clássica, é uma sinfonia de sabores em camadas. Biscoitos champanhe embebidos em café expresso se misturam com um creme rico de queijo mascarpone. Polvilhado com cacau em pó, cada garfada é uma experiência harmoniosa de amargor, doçura e cremosidade. Uma homenagem à tradição italiana, o tiramisu é mais do que uma sobremesa; é uma jornada sensorial que encanta o paladar em cada mordida."
            :imagem="imagem2"
        />
        
    </div>
</template>

<style>
.post{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  
}
</style>