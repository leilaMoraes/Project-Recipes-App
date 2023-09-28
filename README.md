# ⭐ Boas-Vindas ao Repositório Recipes App 🥘
> *Clique nas setas para ver mais* 
<details>
<summary><strong>👩‍💻 O Que Foi Desenvolvido</strong></summary><br />

Este é um projeto de app de receitas, desenvolvido em grupo e que utiliza React Hooks e Context API.

O projeto consistiu em desenvolver um sistema que permite visualizar, buscar, filtrar, favoritar, compartilhar e acompanhar o processo de preparação de receitas e drinks.

A base de dados foram 2 APIs distintas, uma para comidas e outra para bebidas.

O layout tem como foco dispositivos móveis, dessa forma todos os protótipos vão estar desenvolvidos em telas menores.

<div align="center">
<img src="https://github.com/leilaMoraes/Project-Recipes-App/assets/109045940/2d1b222b-1d79-40c9-8146-526e8314cfb2" /><br />
Imagem ilustrativa disponibilizada pela Trybe
</div>
</details>

<details>
<summary><strong>👀 Para Rodar Localmente</strong></summary><br />

1. Clone o repositório   
  `git clone git@github.com:leilaMoraes/Project-Recipes-App.git`
2. Navegue até a pasta do repositório clonado  
    `cd Project-Recipes-App`
3. Instale as dependências no diretório raiz  
  `npm install`
</details>

<details>
<summary><strong>⚙️ APIs</strong></summary><br/>

 <details><summary><b> TheMealDB API</b></summary><br/>

O [TheMealDB](https://www.themealdb.com/) é um banco de dados aberto, mantido pela comunidade, com receitas e ingredientes de todo o mundo.

Os end-points são bastante ricos, você pode [vê-los aqui](https://www.themealdb.com/api.php)

O modelo de resposta para uma `meal` é o seguinte:
    
  <details><summary><b>Ver modelo de resposta para uma meal</b></summary>

          {
            "meals":[
                {
                  "idMeal":"52882",
                  "strMeal":"Three Fish Pie",
                  "strDrinkAlternate":null,
                  "strCategory":"Seafood",
                  "strArea":"British",
                  "strInstructions":"Preheat the oven to 200C\/400F\/Gas 6 (180C fan).\r\nPut the potatoes into a saucepan of cold salted water. Bring up to the boil and simmer until completely tender. Drain well and then mash with the butter and milk. Add pepper and taste to check the seasoning. Add salt and more pepper if necessary.\r\nFor the fish filling, melt the butter in a saucepan, add the leeks and stir over the heat. Cover with a lid and simmer gently for 10 minutes, or until soft. Measure the flour into a small bowl. Add the wine and whisk together until smooth.\r\nAdd the milk to the leeks, bring to the boil and then add the wine mixture. Stir briskly until thickened. Season and add the parsley and fish. Stir over the heat for two minutes, then spoon into an ovenproof casserole. Scatter over the eggs. Allow to cool until firm.\r\nSpoon the mashed potatoes over the fish mixture and mark with a fork. Sprinkle with cheese.\r\nBake for 30-40 minutes, or until lightly golden-brown on top and bubbling around the edges.",
                  "strMealThumb":"https:\/\/www.themealdb.com\/images\/media\/meals\/spswqs1511558697.jpg",
                  "strTags":"Fish,Seafood,Dairy,Pie",
                  "strYoutube":"https:\/\/www.youtube.com\/watch?v=Ds1Jb8H5Sg8",
                  "strIngredient1":"Potatoes",
                  "strIngredient2":"Butter",
                  "strIngredient3":"Milk",
                  "strIngredient4":"Gruy\u00e8re",
                  "strIngredient5":"Butter",
                  "strIngredient6":"Leek",
                  "strIngredient7":"Plain Flour",
                  "strIngredient8":"White Wine",
                  "strIngredient9":"Milk",
                  "strIngredient10":"Parsley",
                  "strIngredient11":"Salmon",
                  "strIngredient12":"Haddock",
                  "strIngredient13":"Smoked Haddock",
                  "strIngredient14":"Eggs",
                  "strIngredient15":"",
                  "strIngredient16":"",
                  "strIngredient17":"",
                  "strIngredient18":"",
                  "strIngredient19":"",
                  "strIngredient20":"",
                  "strMeasure1":"1kg",
                  "strMeasure2":"Knob",
                  "strMeasure3":"Dash",
                  "strMeasure4":"50g",
                  "strMeasure5":"75g",
                  "strMeasure6":"2 sliced",
                  "strMeasure7":"75g",
                  "strMeasure8":"150ml",
                  "strMeasure9":"568ml",
                  "strMeasure10":"2 tbs chopped",
                  "strMeasure11":"250g",
                  "strMeasure12":"250g",
                  "strMeasure13":"250g",
                  "strMeasure14":"6",
                  "strMeasure15":"",
                  "strMeasure16":"",
                  "strMeasure17":"",
                  "strMeasure18":"",
                  "strMeasure19":"",
                  "strMeasure20":"",
                  "strSource":"https:\/\/www.bbc.co.uk\/food\/recipes\/three_fish_pie_58875",
                  "dateModified":null
                }
            ]
          }
    
Os ingredientes seguem uma ordem lógica onde o nome dele (<code>strIngredient1</code>) e a quantidade (<code>strMeasure1</code>) tem o mesmo número no final (1, nesse caso).

É possível listar todas as `categorias`, `nacionalidades` (vindas da API como "areas") e `ingredientes`:

      categorias: https://www.themealdb.com/api/json/v1/1/list.php?c=list
      nacionalidades: https://www.themealdb.com/api/json/v1/1/list.php?a=list
      ingredientes: https://www.themealdb.com/api/json/v1/1/list.php?i=list

As fotos dos ingredientes vêm de um end-point padronizado com a seguinte lógica:

      https://www.themealdb.com/images/ingredients/{nome-do-ingrediente}-Small.png
      // exemplo com "Lime"
      https://www.themealdb.com/images/ingredients/Lime-Small.png
    
  </details>
 </details>

 <details><summary><b> The CockTailDB API</b></summary><br/>

Bem similar (inclusive mantida pela mesma entidade) a TheMealDB API, só que focado em bebidas.

Os end-points também são bastante ricos, você pode [vê-los aqui](https://www.thecocktaildb.com/api.php)

As respostas seguem a mesma estrutura, com algumas particularidades relativas às bebidas (como ser ou não alcoólica, por exemplo)

  <details><summary><b>Ver modelo de resposta para drinks</b></summary>

          {
            "drinks":[
                {
                  "idDrink":"17256",
                  "strDrink":"Martinez 2",
                  "strDrinkAlternate":null,
                  "strDrinkES":null,
                  "strDrinkDE":null,
                  "strDrinkFR":null,
                  "strDrinkZH-HANS":null,
                  "strDrinkZH-HANT":null,
                  "strTags":null,
                  "strVideo":null,
                  "strCategory":"Cocktail",
                  "strIBA":null,
                  "strAlcoholic":"Alcoholic",
                  "strGlass":"Cocktail glass",
                  "strInstructions":"Add all ingredients to a mixing glass and fill with ice.\r\n\r\nStir until chilled, and strain into a chilled coupe glass.",
                  "strInstructionsES":null,
                  "strInstructionsDE":"Alle Zutaten in ein Mischglas geben und mit Eis f\u00fcllen. Bis zum Abk\u00fchlen umr\u00fchren und in ein gek\u00fchltes Coup\u00e9glas abseihen.",
                  "strInstructionsFR":null,
                  "strInstructionsZH-HANS":null,
                  "strInstructionsZH-HANT":null,
                  "strDrinkThumb":"https:\/\/www.thecocktaildb.com\/images\/media\/drink\/fs6kiq1513708455.jpg",
                  "strIngredient1":"Gin",
                  "strIngredient2":"Sweet Vermouth",
                  "strIngredient3":"Maraschino Liqueur",
                  "strIngredient4":"Angostura Bitters",
                  "strIngredient5":null,
                  "strIngredient6":null,
                  "strIngredient7":null,
                  "strIngredient8":null,
                  "strIngredient9":null,
                  "strIngredient10":null,
                  "strIngredient11":null,
                  "strIngredient12":null,
                  "strIngredient13":null,
                  "strIngredient14":null,
                  "strIngredient15":null,
                  "strMeasure1":"1 1\/2 oz",
                  "strMeasure2":"1 1\/2 oz",
                  "strMeasure3":"1 tsp",
                  "strMeasure4":"2 dashes",
                  "strMeasure5":null,
                  "strMeasure6":null,
                  "strMeasure7":null,
                  "strMeasure8":null,
                  "strMeasure9":null,
                  "strMeasure10":null,
                  "strMeasure11":null,
                  "strMeasure12":null,
                  "strMeasure13":null,
                  "strMeasure14":null,
                  "strMeasure15":null,
                  "strCreativeCommonsConfirmed":"No",
                  "dateModified":"2017-12-19 18:34:15"
                }
            ]
          }

Os ingredientes seguem uma ordem lógica onde o nome dele (<code>strIngredient1</code>) e a quantidade (<code>strMeasure1</code>) tem o mesmo número no final (1, nesse caso).
  </details>
 </details>
</details>

## Desenvolvedores

<a href="https://github.com/leilaMoraes/Project-Recipes-App/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=leilaMoraes/Project-Recipes-App" />
</a>

## Requisitos do Projeto

1. Desenvolva os testes unitários de maneira que a cobertura seja de, no mínimo, 90%. ✖️
2. Crie todos os elementos que devem respeitar os atributos descritos no protótipo para a tela de login. ✔️
3. Desenvolva a tela de maneira que a pessoa consiga escrever seu email no input de email e sua senha no input de senha. ✔️
4. Desenvolva a tela de maneira que o formulário só seja válido após um email válido e uma senha de mais de 6 caracteres serem preenchidos. ✔️
5. Após a submissão do formulário, salve no localStorage o e-mail da pessoa usuária na chave `user`. ✔️
6. Redirecione a pessoa usuária para a tela principal de receitas de comidas após a submissão e validação com sucesso do login. ✔️
7. Implemente o header de acordo com a necessidade de cada tela. ✔️
8. Redirecione a pessoa usuária para a tela de perfil ao clicar no botão de perfil. ✔️
9. Desenvolva o botão de busca que, ao ser clicado, a barra de busca deve aparecer. O mesmo serve para escondê-la. ✔️
10. Implemente os elementos da barra de busca respeitando os atributos descritos no protótipo. ✔️
11. Implemente 3 radio buttons na barra de busca: Ingredient, Name e First letter. ✔️
12. Busque na API de comidas caso a pessoa esteja na página de comidas, e na API de bebidas caso esteja na de bebidas. ✔️
13. Redirecione para a tela de detalhes da receita caso apenas uma receita seja encontrada, com o ID da mesma na URL. ✔️
14. Caso a busca retorne mais de uma receita, renderize as 12 primeiras encontradas, exibindo a imagem e o nome de cada uma. ✔️
15. Exiba um `alert` caso nenhuma receita seja encontrada. ✔️
16. Implemente o menu inferior posicionando-o de forma fixa e contendo 2 ícones: um para comidas e outro para bebidas. ✔️
17. Exiba o menu inferior apenas nas telas indicadas pelo protótipo. ✔️
18. Redirecione a pessoa usuária para a tela correta ao clicar em cada ícone no menu inferior. ✔️
19. Carregue as 12 primeiras receitas de comidas ou bebidas, uma em cada card. ✔️
20. Implemente os botões de categoria para serem utilizados como filtro. ✔️
21. Implemente o filtro das receitas por meio da API ao clicar no filtro de categoria. ✔️
22. Implemente o filtro como um toggle, o qual se for selecionado novamente, o app deve retornar as receitas sem nenhum filtro. ✔️
23. Redirecione a pessoa usuária ao clicar no card para a tela de detalhes, que deve mudar a rota e conter o id da receita na URL. ✖️
24. Realize uma request para a API passando o `id` da receita que deve estar disponível nos parâmetros da URL. ✔️
25. Desenvolva a tela de modo que contenha uma imagem da receita, o título, a categoria em caso de comidas e se é ou não alcoólico em caso de bebidas, uma lista de ingredientes seguidos pelas quantidades, instruções, um vídeo do youtube incorporado e recomendações. ✔️
26. Implemente as recomendações. Para receitas de comida, a recomendação deverá ser bebida, já para as receitas de bebida a recomendação deverá ser comida. ✔️
27. Implemente os 6 cards de recomendação, mostrando apenas 2. O scroll é horizontal, similar a um `carousel`. ✔️
28. Desenvolva um botão de nome "Start Recipe" que deve ficar fixo na parte de baixo da tela o tempo todo. ✔️
29. Implemente a solução de forma que, caso a receita já tenha sido feita, o botão "Start Recipe" desapareça. ✔️
30. Implemente a solução de modo que, caso a receita tenha sido iniciada mas não finalizada, o texto do botão deve ser "Continue Recipe". ✔️
31. Redirecione a pessoa usuária caso o botão "Start Recipe" seja clicado, a rota deve mudar para a tela de receita em progresso. ✔️
32. Implemente um botão de compartilhar e um de favoritar a receita. ✔️
33. Implemente a solução de forma que, ao clicar no botão de compartilhar, o link da receita dentro do app deve ser copiado para o clipboard e uma mensagem avisando que o link foi copiado deve aparecer. ✔️
34. Salve as receitas favoritas no `localStorage` na chave `favoriteRecipes`. ✔️
35. Implemente o ícone do coração (favorito) de modo que: deve vir preenchido caso a receita esteja favoritada e "despreenchido" caso contrário. ✔️
36. Implemente a lógica no botão de favoritar. Caso seja clicado, o ícone do coração deve mudar seu estado atual, caso esteja preenchido deve mudar para "despreenchido" e vice-versa. ✖️
37. Desenvolva a tela de modo que contenha uma imagem da receita, o título, a categoria em caso de comidas e se é ou não alcoólico em caso de bebidas, uma lista de ingredientes com suas respectivas quantidades e instruções. ✔️
38. Desenvolva um checkbox para cada item da lista de ingredientes. ✔️
39. Implemente uma lógica que ao clicar no checkbox de um ingrediente, o nome dele deve ser "riscado" da lista. ✔️
40. Salve o estado do progresso, que deve ser mantido caso a pessoa atualize a página ou volte para a mesma receita. ✖️
41. Desenvolva a lógica de favoritar e compartilhar. A lógica da tela de detalhes de uma receita se aplica aqui. ✖️
42. Implemente a solução de modo que o botão de finalizar receita ("Finish Recipe") só pode estar habilitado quando todos os ingredientes estiverem _"checkados"_ (marcados). ✔️
43. Redirecione a pessoa usuária após clicar no botão de finalizar receita ("Finish Recipe"), para a página de receitas feitas, cuja rota deve ser `/done-recipes`. ✖️
44. Implemente os elementos da tela de receitas feitas respeitando os atributos descritos no protótipo. ✔️
45. Desenvolva a tela de modo que, caso a receita do card seja uma comida, ela deve possuir: a foto da receita, nome, categoria, nacionalidade, a data em que a pessoa fez a receita, as 2 primeiras tags retornadas pela API e um botão de compartilhar. ✔️
46. Desenvolva a tela de maneira que, caso a receita do card seja uma bebida, ela deve possuir: a foto da receita, o nome, se é alcoólica, a data em que a pessoa fez a receita e um botão de compartilhar. ✔️
47. Desenvolva a solução de modo que o botão de compartilhar deve copiar a URL da tela de detalhes da receita para o clipboard. ✔️
48. Implemente 2 botões que filtram as receitas por comida ou bebida e um terceiro que remove todos os filtros. ✔️
49. Redirecione para a tela de detalhes da receita caso seja clicado na foto ou no nome da receita. ✔️
50. Implemente os elementos da tela de receitas favoritas (cumulativo com os atributos em comum com a tela de receitas feitas), respeitando os atributos descritos no protótipo. ✔️
51. Desenvolva a tela de modo que, caso a receita do card seja uma comida, ela deve possuir: a foto da receita, nome, categoria, nacionalidade, um botão de compartilhar e um de "desfavoritar". ✔️
52. Desenvolva a tela de modo que, caso a receita do card seja uma bebida, ela deve possuir: a foto da receita, nome, se é alcoólica ou não, um botão de compartilhar e um de "desfavoritar". ✖️
53. Desenvolva a solução de modo que o botão de compartilhar deve copiar a URL da tela de detalhes da receita para o clipboard. ✔️
54. Desenvolva a solução de modo que o botão de "desfavoritar" deve remover a receita da lista de receitas favoritas do `localStorage` e da tela. ✖️
55. Implemente 2 botões que filtram as receitas por comida ou bebida e um terceiro que remove todos os filtros. ✔️
56. Redirecione a pessoa usuária ao clicar na foto ou no nome da receita, a rota deve mudar para a tela de detalhes daquela receita. ✖️
57. Implemente os elementos da tela de perfil respeitando os atributos descritos no protótipo. ✔️
58. Implemente a solução de maneira que o e-mail da pessoa usuária deve estar visível. ✔️
59. Implemente 3 botões: um de nome "Done Recipes", um de nome "Favorite Recipes" e um de nome "Logout". ✔️
60. Redirecione a pessoa usuária que, ao clicar no botão de "Done Recipes", a rota deve mudar para a tela de receitas feitas. ✔️
61. Redirecione a pessoa usuária que, ao clicar no botão de "Favorite Recipes", a rota deve mudar para a tela de receitas favoritas. ✔️
62. Redirecione a pessoa usuária que ao clicar no botão de "Logout", o `localStorage` deve ser limpo e a rota deve mudar para a tela de login. ✔️
