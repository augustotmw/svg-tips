# svg-tips

## Pesquisa sobre desenvolvimento e dicas sobre SVG

### Índice

1. [Referências](#referencias)
2. Básico - [`<svg></svg>` - Tag principal](#)
    1. [Sintaxe](#sintaxe)
    2. 


<a id="referencias"></a>

---

### Referências

- Sara Soueidan, SVG Wizard level 100:
  - [Sistemas de coordenadas](http://www.sarasoueidan.com/blog/svg-coordinate-systems/)
- [svgtutorial.com](http://svgtutorial.com/)
- [Lista de atributos compartilhados e não com o CSS](http://slides.com/sarasoueidan/styling-animating-svgs-with-css#/10)

### Ferramentas

- [Exemplo interativo da mestre Sara Soueidan](http://www.sarasoueidan.com/demos/interactive-svg-coordinate-system/)


### Bibliotecas

- [@daneden's animate.css, biblioteca de animações css](https://daneden.github.io/animate.css/)
- [Dmitry Baranovsky's Snap.svg, Js SVG lib](http://snapsvg.io/)
- [Anime.js, JS Animation Engine](http://animejs.com/)


---

### Para ler depois:

- (https://codyhouse.co/gem/animate-svg-icons-with-css-and-snap/)
- (https://www.youtube.com/watch?v=lf7L8X6ZBu8&list=PL37ZVnwpeshHAnqFlTxhd0MIXWjLBbM3R&index=4)
- (https://www.sitepoint.com/tips-accessible-svg/)
- (https://svgontheweb.com/)
- (https://css-tricks.com/guide-svg-animations-smil/)

#### path
- (https://www.dashingd3js.com/svg-paths-and-d3js)


#### gradiente no SVG
- (https://fvsch.com/svg-gradient-fill/)
- (https://stackoverflow.com/questions/25500159/how-to-get-gradient-color-fill-in-bar-pie-area-charts-using-c3js?rq=1)
  - Utilizando D3.js

```javascript
oninit: function () {

  d3.select('svg').append("linearGradient")
    .attr("id", "timeframe-gradient")
    .attr("gradientUnits", "userSpaceOnUse")
    .attr("x1", 0).attr("y1", 0)
    .attr("x2", 0).attr("y2", 100)
    .selectAll("stop")
    .data([
      {offset: "60%", color: "#666", opacity: 0},
      {offset: "100%", color: "#666", opacity: 1}
    ])
    .enter().append("stop")
    .attr("offset", function(d) { return d.offset; })
    .attr("stop-color", function(d) { return d.color; })
    .attr("stop-opacity", function(d) { return d.opacity;});

}

```

```css
.event-timeframe {
  rect {
    fill: url(#timeframe-gradient);
  }
}
```

- ()
- ()
- ()
- ()
- ()
- ()
- ()