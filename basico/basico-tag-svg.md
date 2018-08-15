# SVG - Scalable Vector Graphics

## Índice

1. [Sintaxe](#sintaxe)
2. [Tips](#tips)
3. [Atributos](#svgattrs)



<a id="#sintaxe"></a>

---

## Sintaxe

```html

<svg></svg>

```

<a id="#tips"></a>

---

## Tips

- Gera a tela, o canvas, a área de renderização do SVG e nela gera o viewport (área visível);
- Parafraseando a [Sara Soueidan](http://www.sarasoueidan.com/), wizard SVG level 100,  super-referência em SVG:

  >"*The __viewport__ is the viewing area where the SVG will be visible. You can think of the __viewport__ as a window through which you can see a particular scene. The scene may be entirely or partially visible through that window.*"

    ou seja: "**O _viewport_ é a área de visualização onde o SVG será visível. Você pode pensar no viewport como uma janela através de onde você pode ver uma cena particular. A cena pode ser inteira ou parcialmente visível através desta janela.**";
- Para **_width_** e **_height_** a unidade padrão é o pixel (**_px_**), porém podemos utilizar também as unidades: **_em, ex, px, pt, pc, cm, mm, in, e %_**;
- Ao carregar o SVG, os navegadores estabelecem um valor inicial para **ambos** os seus sistemas de coordenadas:
  - **_viewport coordinate system_** (coordenadas do *viewport*): Plano Cartesiano (eixo **_x,y_**) inicial, com a interseção de seus eixos (seu ponto 0,0) no canto esquerdo superior do elemento `<svg></svg>`;
  - **_user coordinate system_** (coordenadas do *viewbox*): Plano Cartesiano (eixo **_x,y_**) que inicialmente tem o sua interseção de eixos igual ao do cartesiano do *viewport*, canto esquerdo superior do elemento `<svg></svg>`, porém pode ser alterado via o atributo `viewBox` desta tag;


<a id="svgattrs"></a>

---

## Atributos

- **width**: largura do *viewport*;
- **height**: altura do *viewport*;
- **viewBox**: sistema de coordenadas de usuário **(_user coordinate system_)**. [Mais detalhes abaixo](#viewboxDetails);
- **preserveAspectRatio**: uilizado para manter uniforme e preservando as proporções do redimensionamento do grupo de vetores. [Mais detalhes abaixo](#preservAspectRatioDetails);

<a id="#viewboxDetails"></a>

---

## `viewBox` - O manipulador de visualização

### Sintaxe

```html
  <svg viewBox="[x] [y] [w] [h]"></svg>
```

Onde:

- **x** :  Altera a posição horizontal da interseção de eixos do *viewBox* estará dentro do *viewport*;
- **y** : Altera a posição vertical da interseção de eixos do *viewBox* estará dentro do *viewport*;
- **w** : Altera a largura de todo o conjunto de elementos visíveis dentro do *viewport*;
- **h** : Altera a altura de todo o conjunto de elementos visíveis dentro do *viewport*;

### Tips

- O *viewBox* funciona como se fosse a tela inteira, o canvas inteiro, da imagem, fazendo do *viewport* uma espécie de "janela" que se move pela tela e ao se redimensionar, aplica zoom na mesma. (Assim como o navegador se comporta em relação ao mapa no Google Maps, sendo o mapa o canvas inteiro e o navegador somente o viewport).

### Exemplo do viewBox

<svg width="700" height="300"><text x="22%" y="30" style="fill:blue;"> viewport: width = 100px, height = 100px</text><g><circle r="25" cx="80" cy="100" fill="green"></circle><circle r="25" cx="120" cy="100" fill="yellow"></circle><circle r="25" cx="100" cy="140" fill="darkblue"></circle><rect x="50" y="70" width="100" height="100" style="stroke: blue; stroke-width: 1px; fill: transparent;" /><rect x="51" y="71" width="98" height="98" style="stroke: red; stroke-width: 1px; fill: transparent;" /><text x="30" y="200" style="fill: red;"> viewBox indefinido ou</text><text x="30" y="220" style="fill: red;"> viewBox="0 0 100 100"</text></g><g><circle r="37.5" cx="285" cy="135" fill="green"></circle><circle r="37.5" cx="345" cy="135" fill="yellow"></circle><circle r="37.5" cx="315" cy="195" fill="darkblue"></circle><rect x="270" y="70" width="100" height="100" style="stroke: blue; stroke-width: 1px; fill: transparent;" /><rect x="240" y="90" width="150" height="150" style="stroke: red; stroke-width: 1px; fill: transparent;" /><text x="240" y="270" style="fill: red;"> viewBox="30 -20 75 75"</text></g><g><circle r="12.5" cx="535" cy="75" fill="green"></circle><circle r="12.5" cx="555" cy="75" fill="yellow"></circle><circle r="12.5" cx="545" cy="94" fill="darkblue"></circle><rect x="490" y="70" width="100" height="100" style="stroke: blue; stroke-width: 1px; fill: transparent;" /><rect x="520" y="60" width="50" height="50" style="stroke: red; stroke-width: 1px; fill: transparent;" /><text x="460" y="200" style="fill: red;"> viewBox="-30 10 150 150"</text></g></svg>
#### Codigo do exemplo

```html
<svg width="700" height="300">

  <text x="22%" y="30" style="fill:blue;"> viewport: width = 100px, height = 100px</text>

  <g>
    <circle r="25" cx="80" cy="100" fill="green"></circle>
    <circle r="25" cx="120" cy="100" fill="yellow"></circle>
    <circle r="25" cx="100" cy="140" fill="darkblue"></circle>              
    <rect x="50" y="70" width="100" height="100" style="stroke: blue; stroke-width: 1px; fill: transparent;" />
    <rect x="51" y="71" width="98" height="98" style="stroke: red; stroke-width: 1px; fill: transparent;" />

    <text x="30" y="200" style="fill: red;"> viewBox indefinido ou</text>
    <text x="30" y="220" style="fill: red;"> viewBox="0 0 100 100"</text>
  </g>

  <g>
    <circle r="37.5" cx="285" cy="135" fill="green"></circle>
    <circle r="37.5" cx="345" cy="135" fill="yellow"></circle>
    <circle r="37.5" cx="315" cy="195" fill="darkblue"></circle>

    <rect x="270" y="70" width="100" height="100" style="stroke: blue; stroke-width: 1px; fill: transparent;" />
    <rect x="240" y="90" width="150" height="150" style="stroke: red; stroke-width: 1px; fill: transparent;" />

    <text x="240" y="270" style="fill: red;"> viewBox="30 -20 75 75"</text>

  </g>


  <g>
    <circle r="12.5" cx="535" cy="75" fill="green"></circle>
    <circle r="12.5" cx="555" cy="75" fill="yellow"></circle>
    <circle r="12.5" cx="545" cy="94" fill="darkblue"></circle>

    <rect x="490" y="70" width="100" height="100" style="stroke: blue; stroke-width: 1px; fill: transparent;" />
    <rect x="520" y="60" width="50" height="50" style="stroke: red; stroke-width: 1px; fill: transparent;" />

    <text x="460" y="200" style="fill: red;"> viewBox="-30 10 150 150"</text>

  </g>

</svg>

```

## `preserveAspectRatio` - O equalizador de proporções

### Sintaxe

```html

  <svg preserveAspectRatio="[defer]? [align] [meet|slice]?"></svg>
  
```
  
  Onde:

- **defer** (opcional): usado quando se aplica o svg em uma imagem; //pesquisar mais sobre
- **align**: indica se irá ou não forçar o redimensionamento uniforme e, caso seja, aonde ficará alinhado o vetor no caso de o tamanho do viewBox não coincidir com o do viewport;
  - Caso o valor deste parâmetro seja "none", o vetor será redimensionado, "esticado", para atingir as margens do viewport, não preservando as proporções uniformes;
  - Todos os demais valores irão preservar as proporções uniformes e já indicarão onde no viewport será ancorado o alinhamento, o comportamento do posicionamento é parecido com o funcionamento da propriedade CSS "background-position";
  - Valores possíveis:
    - **none**: o vetor será redimensionado, "esticado", para atingir as margens do viewport, não preservando as proporções uniformes;
    - **xMinYMin**: equivalente à *"background-position: 0% 0%;";*
    - **xMinYMid**: equivalente à *"background-position: 0% 50%;";*
    - **xMinYMax**: equivalente à *"background-position: 0% 100%;*";
    - **xMidYMin**: equivalente à *"background-position: 50% 0%;"*
    - **xMidYMid**: equivalente à *"background-position: 50% 50%;*" _**(valor default)**_;
    - **xMidYMax**: equivalente à *"background-position: 50% 100%;*";
    - **xMaxYMin**: equivalente à *"background-position: 100% 0%;*";
    - **xMaxYMid**: equivalente à *"background-position: 100% 50%;*";
    - **xMaxYMax**: equivalente à *"background-position: 100% 100%;"*;

- **meet|slice _(default: "meet")_**: define que viewBox deve ter as arestas de suas dimensões relativas às arestas dimensionais do viewport. Funciona de forma similar à propriedade css "_**background-size**_", onde o valor "_**contain**_" equivale ao "_**meet**_" e o valor "_**cover**_" é equivalente ao "_**slice**_";
  - Exemplo: 
    
    <svg width="500" height="200"><text x="30" y="10" style="fill: green;">meet / contain</text><text x="50" y="40" fill="blue">viewport</text><rect x="30" y="50" width="100" height="100" fill="transparent" stroke="blue" /><text x="75" y="-140" fill="red" transform="rotate(90)">viewBox</text><rect x="31" y="75" width="99" height="50" fill="transparent" stroke="red"></rect><text x="250" y="10" fill="green">slice / cover</text><text x="270" y="40" fill="blue">viewport</text><rect x="250" y="50" width="100" height="100" fill="transparent" stroke="blue" /><rect x="220" y="51" width="160" height="98" fill="transparent" stroke="red"></rect><text x="75" y="-390" fill="red" transform="rotate(90)">viewBox</text></svg>

    <div>
    
    </div>

    código do exemplo:

    ```html
      <svg width="500" height="200">
        <text x="30" y="10" style="fill: green;">meet / contain</text>
        <text x="50" y="40" fill="blue">viewport</text>

        <rect x="30" y="50" width="100" height="100" fill="transparent" stroke="blue" />

        <text x="75" y="-140" fill="red" transform="rotate(90)">viewBox</text>
        <rect x="31" y="75" width="99" height="50" fill="transparent" stroke="red"></rect>


        <text x="250" y="10" fill="green">slice / cover</text>
        <text x="270" y="40" fill="blue">viewport</text>
        <rect x="250" y="50" width="100" height="100" fill="transparent" stroke="blue" />
        <rect x="220" y="51" width="160" height="98" fill="transparent" stroke="red"></rect>
        <text x="75" y="-390" fill="red" transform="rotate(90)">viewBox</text>
      </svg>
    ```
