# Box Model

É fundamental para fazer layouts para a web, pois possibilita maior facilidade para aplicar o CSS. F

O box model é uma caixa retangular. Essa caixa possui propriedades de uma caixa 2D, sendo:

- Tamanho (largura/altura): width | height;
- Conteúdo: content;
- Bordas: border;
- Preenchimento interno: padding;
- Espaços fora da caixa: margin.

Cada elemento na página será considerado uma caixa.

### Box Sizing

É responsável pelo cálculo total do tamanho da caixa.

O cálculo é feito por:

- content-box | border-box

```CSS
div {
  box-sizing: border-box;
}
```

Exemplo prático:

```HTML
<div>
  CSS é incrível!
</div>
```

```CSS
div {
  width: 100px;
  height: 100px;
  border: 1px solid red;
}
```

Nesse momento, estamos vendo 100 pixels.

Agora, se eu adiciono `margin: 10%`, perceba que a caixa é "empurrada" do ponto em que estava. Vamos colocar também um padding de 20px somente nas laterais, que vai ser o preenchimento interno delas. Isso vai fazer a caixa aumentar seu tamanho.

```CSS
div {
  width: 100px;
  height: 100px;
  border: 1px solid red;
  margin: 10%;
  padding: 0 20px;
}
```

Logo, não temos mais o respeito aos 100px, pois o o cálculo do tamanho total da caixa é feito pelo `content-box`, ou seja, os 100px estão aplicados ao conteúdo da caixa.

Quando ponho 20px de preenchimento nas laterais, essa caixa soma os 20px e, ao todo, temos uma caixa de 140px de largura se contarmos de uma borda a outra, apesar da contagem ser através do conteúdo.

Para fazer com que os 100px seja verdadeiramente 100px e não se transforme em 140px, a contagem pode ser feita através da propriedade `box-sizing: border-box`.

Ele faz um cálculo para que a largura continue 100px, mas adicionando os 20px de padding nas laterais:

```CSS
div {
  width: 100px;
  height: 100px;
  border: 1px solid red;
  margin: 10%;
  padding: 0 20px;
  box-sizing: border-box;
}
```

Em muitos códigos, é comum ver o desenvolvedor adicionar uma linha assim:

```CSS
* {
  box-sizing: border-box;
}
```

Isso faz com que todos os conteúdos sejam calculados a partir da borda para que não atrapalhe na montagem do layout.

### Display: block e inline

O display é a apresentação das caixas; como as caixas se comportam em relação às outras caixas, representando o comportamento externo dessas caixas.

Por exemplo, se eu tenho duas caixas, elas estão uma em cima da outra? Uma ao lado da outra? Como é esse comportamento?

Alguns conteúdos por padrão já são `display: block;` e outros `display: inline`.

Exemplos de utilização padrão:

- block -
  `<p> <div> <section>`, todos os headings `<h1>, <h2>`...
- inline - `<a> <strong> <span> <em>`...

| **block**                                                           | **inline**                                                   |
| ------------------------------------------------------------------- | ------------------------------------------------------------ |
| Ocupa toda a linha, colocando o <Br>próximo elemento abaixo desse.¹ | Elemento ao lado do outro.                                   |
| width e height são respeitados.                                     | width e height não funcionam.                                |
| padding, margin e border <Br>funcionarão normalmente.               | Somente valores horizontais<br> de margin, padding e border. |

¹ Ou seja, sempre que vir uma caixa abaixo da outra, é `display: block;`, pois ela empurra outras caixas abaixo dela. Se estiver ao lado da outra, é `display: inline`.

Exemplos práticos:

```HTML
<div>Um conteúdo</div> outro conteúdo
```

Uma `<div>`, por padrão, é `display: block;`. Então, essa frase "outro conteúdo" ficaria abaixo de "um conteúdo" e não ao lado.

```HTML
<p>Um texto <strong>em negrito</strong>, por exemplo.</p>
```

Já no caso acima, a tag `<strong>` não empurrou o final da frase para baixo, sendo assim uma tag com `display: inline;`.

Se eu colocasse:

```HTML
<p>Um <div>texto</div> <strong>em negrito</strong>, por exemplo.</p>
```

"Texto" seria empurrado para baixo, deixando um espaço acima e a frase "em negrito, por exemplo." na linha debaixo; fazendo com que ele ocupasse uma linha inteira.

#### div x span

O span se comportante como inline e, sendo assim, não respeita largura e nem altura, diferentemente da div, que tem comportamento `display: block`:

```HTML
<div>block</div>

<span>inline</span>
```

```CSS
div {
  height: 100px;
  width: 10px;
  border: 1px solid red;
}

span {
  height: 100px;
  width: 10px;
  border: 1px solid purple;
}
```

Para fazer com que o `span` tenha esse comportamento similar ao da `div`, é necessário incluir ao CSS `display: block;`.

```CSS
div {
  height: 100px;
  width: 10px;
  border: 1px solid red;
}

span {
  height: 100px;
  width: 10px;
  border: 1px solid purple;
  display: block;
}
```

Como visto acima, quando há `display: block;`, `padding`, `margin` e `border` funcionam normalmente, enquanto no `display: inline` somente os valores horizontais destes são válidos.

Vejamos:

```HTML
<div>block</div>

<span>inline</span>
```

```CSS
div {
  margin: 20px; //empurra para os lados, topo e baixo
}

span {
  margin: 20px; //empurra para as laterais, pois não respeita o margin de cima e de baixo
}
```

### Margin

### Padding

### Border-outline
