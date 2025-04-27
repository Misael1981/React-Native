# Como funciona o SVG no React Native?

Adicionamos arquivos SVG no nosso projeto e, para usá-los na aplicação, decidimos recorrer à biblioteca `react-native-svg`.

Mas aí vem a dúvida: já que o SVG é um tipo de imagem, por que não usamos simplesmente o componente `<Image>` para colocá-lo na nossa aplicação?

Vem comigo que vou te explicar tudo!

## O que é SVG e como ele funciona?

SVG (Scalable Vector Graphics) é um tipo de imagem baseada em **código**. A grande vantagem do SVG é que ele não perde qualidade, independentemente do tamanho. Isso acontece porque, ao invés de salvar cada "ponto" da imagem, como nos formatos tradicionais (JPEG ou PNG), o SVG usa formas geométricas como linhas e círculos para desenhar a imagem.

Isso faz com que o SVG seja perfeito para ícones, logotipos e ilustrações, principalmente em telas com diferentes tamanhos e resoluções. E o melhor: por ser baseado em código, ele pode ser facilmente ajustado e personalizado sem a necessidade de programas de edição de imagem. Além disso, em muitos casos, ele ocupa menos espaço, o que ajuda a deixar sites e aplicativos mais rápidos.

## Como o navegador renderiza os SVGs?

Os navegadores interpretam arquivos SVG porque eles são escritos em **XML** (um formato de código). Esse código descreve como a imagem deve ser desenhada, com informações sobre formas, cores, tamanhos e posições.

Com essas instruções, o navegador converte esse código em uma imagem visível. E, como o SVG é baseado em vetores, ele aparece sempre nítido, independente do tamanho da tela.

Entendido como os SVGs funcionam nos navegadores, a dúvida é: como isso é tratado no React Native?

## Como o React Native renderiza elementos gráficos?

No React Native, os elementos gráficos são desenhados diretamente usando APIs nativas de cada plataforma:

No iOS: a renderização gráfica usa o CoreGraphics e Quartz. No Android: a renderização passa pelo Skia via API de desenho do sistema.

O problema é que essas APIs não oferecem um suporte embutido para SVGs, diferentemente do navegador. Cada plataforma tem suas próprias formas de lidar com gráficos vetoriais, mas não há um padrão nativo que o React Native possa usar diretamente para renderizar um como fazemos no HTML.

## Por que não podemos usar SVGs diretamente no React Native?

Como React Native não tem um motor de renderização de SVG próprio, precisamos de uma solução que traduza os elementos SVG para algo que as plataformas móveis entendam. É aí que entra a biblioteca `react-native-svg`.

Ela funciona como uma "ponte" entre os componentes SVG que usamos no JSX e as APIs nativas do iOS e Android, convertendo `<Svg>`, `<Path>`, `<Circle>`, etc., para comandos gráficos específicos de cada plataforma. No iOS, por exemplo, os desenhos são convertidos para CoreGraphics, e no Android, para Skia.

## Conclusão

Sem uma biblioteca que faça essa conversão, a plataforma simplesmente não sabe o que fazer com os SVGs.

Por isso, no React Native, SVGs não são apenas "desenhados" como na web – eles precisam ser traduzidos para formatos compatíveis com cada plataforma. E é exatamente isso que bibliotecas como `react-native-svg` fazem.

Ou seja, sem um motor de renderização próprio, precisamos de uma ponte entre SVG e o ambiente nativo – e é por isso que o suporte não é direto.

### [Voltar ao Menu - React Native: desenvolvendo com Expo](../menu.md)
