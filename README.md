# Vue Router 4 for Everyone
Aplicação feita baseada no curso gratuito [Vue Router 4 for Everyone](https://vueschool.io/courses/vue-router-4-for-everyone) do [VueSchool](https://vueschool.io). 

## Aprendizados

- Vue Router serve para centralizar toda operação de rotas de um site em um só local, além de não precisar da atualização do navegador para ser redirecionado para uma tela.
- Vite se tornou uma ferramenta melhor que o Webpack por causa da sua capacidade de atualizar a aplicação somente com as alterações realmente feitas pelo programador, assim, não demorando tanto para subir a nova versão no dev ou produção.
- `localhost:5173/destinos/:id` é um exemplo de parametrização via GET.
- Lazy Load é uma forma de não carregar o site inteiro dentro de um bundle, mas sim, em arquivos separados. Pra isso ocorrer, deve colocar a chamada do componente como se fosse uma função `() => import('@/Component.vue')`.
- Normalmente em aplicações Js pode ocorrer de ficar com a url com final em hash `https://localhost:5173/#/`. Isso é para que quando solicitasse a página, considere o root verdadeiro do site, porém, atualmente existe uma forma que é _friendly url_ para a aplicação e benéfico ao SEO, que remove isso por padrão.
- Para que o conteúdo de uma página _single_ seja aplicada as alterações de conteúdo, o Vue tem que entender que precisa ser alterado ou com a função `this.$watch(() => variable-to-watch, () => callback-function)` dentro do `created()` ou com a `:key` inserida no `router-view` referenciando para o parametro correto.
- O componente pode receber props da rota ou pela url, até podendo ser alterado ou criado novos props antes de enviar para o componente final.
- Podemos mostrar uma página dentro de outra configurando dentro da rota pai na config `children: []` a config da rota filho. No `<template>` é necessário colocar `<router-view />` para mostrar onde será visualizado.
- Existe formas de criar transições entre _views_ usando `<transition>`, porém, é melhor usar quando realmente for necessário.
- Pode usar uma especie de middleware para verificar se os dados passados de uma rota para outra estão de acordo com o padrão ou valor existente via Guards.
- O Guard pode virar uma espécie de Middleware de rota usando a option `query` para retornar o local onde o usuário quer acessar.
- Para o Composition API, o `this.$route` and `this.$router` podem ser acessados com `useRoute()` and `useRouter()` importados do vue-router.
- No `router` podemos colocar mais de um componente e definir um `default` para ser visualizado como principal e outro nomeado pelo programador para ser renderizado por um `router-view` com name.
- Podemos colocar alias para a rota usando `alias: '/home'` em sua configuração, também podendo usar um array para mais de uma representação.