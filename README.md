Meu guia pessoal de estilo de codificação

## Índice

1. [Introdução](#introdução)
2. [Orientações Gerais](#orientações-gerais)
3. [Legibilidade vs Compressão](#legibilidade-vs-compressão)
4. [Indentação](#indentação)
5. [Suporte do navegador](#suporte-do-navegador)
6. [Frameworks e Libs que eu uso](#frameworks-e-libs-que-eu-uso)
7. [Markup](#markup)
	1. [HTML5](#html5)
	2. [Orientações de marcação](#orientações-de-marcação)
		1. [Etiquetas de fechamento]()
		2. [Aspas duplas]()
		3. [UTF-8 Encoding]()
		4. [Lowercase](#lowercase)
8. [Stylesheets](#stylesheets)
9. [JavaScript](#javascripts)

## Introdução

Eu costumo seguir o que a maioria no mercado segue, a comunidade e grandes corporações como Google, Facebook e Twitter. Por isso montei esse meu guia pessoal de estilo de codificação seguindo esses padrões de mercado, e claro, com um pouco do meu gosto pessoal.

## Orientações Gerais

* Todo o código do front-end deve exibir separação clara de apresentação, conteúdo e comportamento.
* O markup deve ser bem formatado, semanticamente correto e geralmente válido.
* O JavaScript deve melhorar progressivamente (Progressive enhancement) a experiência.

> **Lembre-se:** ==Não há certo ou errado, apenas o que o time decidiu.==

## Legibilidade vs Compressão

Eu prezo pela legibilidade do arquivo que está sendo lido. Não há necessidade do desenvolvedor comprimir o HTML, CSS, JS/JSON propositadamente, o que custa quebrar as chaves de um objeto?

Por esse motivo que foram criados tarefas (gulp, grunt, rake, lambdas, etc) lado do servidor para minificar automaticamente todos os arquivos.

*Ruim*

```html
<header class="site-header"><a href="http://seusite.com">Nome do seu site</a></header>
```

*Bom*

```html
<header class="site-header">
  <a href="http://seusite.com">Nome do seu site</a>
</header>
```

---


*Ruim*

```javascript
module.exports = {
  parserOptions: {sourceType: 'module'},
  env: {browser: true}
  plugins: ['html']
}
```

*Bom*

```javascript
module.exports = {
  parserOptions: {
    sourceType: 'module'
  },
  env: {
    browser: true,
  }
  plugins: [
    'html'
  ]
}
```

---

*Ruim*

```css
.site-paragraph {color:#333;text-transform:uppercase;}
```

*Bom*

```css
.site-paragraph {
  color: #333;
  text-transform: uppercase;
}
```

## Indentação

Use soft tabs com 2 espaços e numca misture espaços com tabs!

Para meus projetos pessoais que envolvem HTML, CSS/SASS e JavaScript eu costumo usar [2 espaços](https://google.github.io/styleguide/htmlcssguide.html#Indentation), mas quando estou trabalhando com um time que cuida desse tipo de discussão eu sigo a risca o a cartilham, se o time decidir usar tabs ou 4 espaços não tem problema.

Eu uso espaços ao invés de tabs porque as tabs nem sempre são exibidas no mesmo tamanho em todos os dispositivos. Os espaços são sempre espaços. :)

*Ruim*

```html
<section class="site-paragraph">
  <p>Lorem ipsum 
	  <code>laboris</code>...
	</p>
</section>
```

*Bom*

```html
<section class="site-paragraph">
  <p>Lorem ipsum <code>laboris</code>...</p>
</section>
```

---

*Ruim*

```css
.site-paragraph {
	color: #333;
  text-transform: uppercase;
     margin-bottom: .5rem;
}
```

*Bom*

```css
.site-paragraph {
  color: #333;
  text-transform: uppercase;
  margin-bottom: .5rem;
}
```


## Suporte do navegador

Como eu trabalho com Progressive enhancement meus projetos abrangem o máximo de navegadores prossívels, mesmo que CSS3, HTML5 e ES6 não sejam suportados pelo IE7/8/9 o HTML, CSS e JS básicos precisam funcionar, mesmo sendo uma definição da empresa não dar suporte para navegadores antigos.

## Frameworks e Libs que eu uso

Eu costumo experimentar o máximo de frameworks e bibliotecas antes de decidir qual usar em um projeto.

As que estou testando e usando atualmente são:

* **SASS** - Folhas de estilo sintaticamente impressionantes :)
* **jQuery** - Uso sempre que posso;
* **Bootstrap 3 e 4** - Trabalho em muitos projetos;
* **Jekyll** - Um gerador de sites estáticos incrível;
* **Middleman** - Outro gerador de sites estáticos bacana, atualmente meu site é feito com ele;
* **Bulma.io** - Estudando a possibilidade de migrar do Bootstrap;
* **Gulpjs** - Meu automatizador de tarefas;
* **VueJS** - Atualmente estudando frenéticamente;
* **Webpack** - Sempre faço algumas coisinhas com esse cara;
* **Babel** - Uso para codificar ECMAScript 6 e dar suporte aos navegadores;
* **React** - Sempre que posso estudo esse cara;
* **Mocha** - Um framework que uso para testes unitários;
* **Chai** - Uma biblioteca para TDD e BDD;
* **Nyc** - Uma interface de linha de comando do **Istanbul** para code coverage;

## Markup

### HTML5

Eu uso **HTML5** desde 2012, quando descobri que podia dar suporte progressivo usando as bibliotecas **[html5shiv](https://github.com/afarkas/html5shiv)** e **[Modernizr](https://modernizr.com/)**.

### Orientações de marcação

Aqui estão algumas dicas do meu estilo de codificar **HTML**. Lembre-se de que ==**isso depende da sua equipe**==, mas você deve aplicá-los uma vez que eles estão decididos. Pense em instalar linters no seu fluxo de trabalho.

#### 1. Etiquetas de fechamento

Sempre feche suas tags. A maioria das tags possui uma tag de abertura e uma tag de fechamento `<span></span>`. Há algumas exceções, entretanto. As etiquetas de auto-fechamento possuem uma barra diagonal. Com o HTML5 isso ficou opcional, então se quiser omita. por exemplo `<hr>`

#### 2. Aspas duplas

Use aspas duplas `""` para todos os valores dos atributos. Quando você precisa colocar aspas duplas dentro de um valor de atributo, use o código de caractere html `&quot;`. Por exemplo:

```html
<input type="textarea" value="&quot;sarcastic air quotes&quot;">
```

#### 3. UTF-8 Encoding

Sempre especifique a codificação de uma página HTML declarando o encoding dentro da tag `<head>`.

```html
<head>
  <meta charset="UTF-8">
</head>
```

#### 4. Lowercase

Use minúsculas em todos os nomes de tags e de atributos.

*Ruim*

```html
<Section CLASs="site-paragraph">
  <P>Lorem ipsum laboris...</P>
</SECTION>
```

*Bom*

```html
<section class="site-paragraph">
  <p>Lorem ipsum laboris...</p>
</section>
```


## Stylesheets

Aqui estão algumas dicas o seu **CSS**. Lembre-se de que ==**isso depende da sua equipe**==, mas você deve aplicá-los uma vez que eles estão decididos. Pense em instalar linters no seu fluxo de trabalho.

### Comentários

### Linha nova no final do arquivo

### Organização

### Componentes

### Ordem de declaração

### Consultas de mídia


## Javascripts









