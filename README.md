# Sass

Aprendendo mais sobre Sass

## Principais tecnologias

* HTML
* CSS

## Pre-requisitos
Extensão: Live Sass Compiler

![Extensão Live Sass Compiler](https://github.com/CaioRibeiroDev/Sass/blob/main/SASS.png)

## Por que usar Sass?

Bom, SASS é uma linguagem de extensão ao CSS que dá um controle mais profissional e dinâmico para suas folhas de estilo, utilizado como um framework para compor o design de uma página. O Sass ajuda muito com a compatibilidade com outros browsers não sendo necessario ficar chamando "-webkit-", "-ms-"... 

## Explicação
Antes de tudo apos baixar a extensão aparecera uma opção no seu "VS CODE" do Sass que é necessario ativar-la.
apos isso é só acompanhar a documentação.

![Sass Extensão](https://github.com/CaioRibeiroDev/Sass/blob/main/image.png)

No HTML é criado três divs para ser usadas como exemplo e dentro de uma delas temos a referencia de um link para demonstração.


```html
<div class="bola1">
    <a href="#" class="a">LINK</a>
</div>
<div class="bola2"></div>
<div class="bola3"></div>
```

Logo começamos a mexer com Sass.

O Exemplo abaixo mostra como são criadas as variaveis, neste caso criamos três variaveis e cada uma com sua devida cor, tanto em hexadecimal quando por extenso.

variaveis
```scss
$primaryColor: #d62424;
$secondaryColor: blue;
$neutraColor: gray;
```

# ---------------------------------------------------------------------------

balls
```scss
.bola1{
    width: 200px;
    height: 200px;
    
    border-radius: 50%;

    background-color: $primaryColor;

    a{
        color: $secondaryColor;
    }

    &:hover {
        background-color: $secondaryColor;
    }
}
```

Já as balls estilizamos como se estivéssemos no proprio arquivo .css, porem com algumas diferenças, no primeiro exemplo criamos uma bola e ja usamos a nossa primeira variavel $primaryColor que significa que estamos setando nosso background-color para cor setada em nossa variavel. Logo acima encontramos algo diferente, nossa classe "a" dentro da classe ".bola1" usando dessa maneira é como se estivéssemos fazendo:

```css
.bola1 {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background-color: #d62424;
}

.bola1 a {
  color: blue;
}

.bola1:hover {
  background-color: blue;
}
```
Não sendo necessario no scss colocar ponto para chamar nossa classa "a" e nosso "hover".

Por fim e não menos importante temos nosso:
```scss
@mixin flexCenter($justify_content, $flex_direction) {
    display: flex;
    justify-content: $justify_content;
    flex-direction: $flex_direction;
    align-items: center;
}
```

mixin digamos que é um metodo que aceita parametros para fazermos modificações direto na chamada.
Neste exemplo acima foi criado um metodo com o nome de flexCenter e é passado dois parametros para ele, dentro de seu escopo colocamos as propriedades css e definimos aonde sera passado os parametros e com isso esta pronto nosso metodo e para ser chamado basta apenas dar um "@include name(params);" como o exemplo abaixo:
```scss
body{
    @include flexCenter(center, column);

    width: 100%;
    height: 100vh;

    background-color: #1a1a1a;
}
```

