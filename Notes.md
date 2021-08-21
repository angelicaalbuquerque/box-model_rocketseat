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

### Display-block-inline

### Margin

### Padding

### Border-outline
