# Default props

Em algumas situações, apenas tornar os componentes completamente independentes pode gerar retrabalho.

Como assim? Vem comigo que vou explicar!

### 1. Quais são os "problemas" das props?

Isto não é um problema exclusivo das props ou do React, mas acontece sempre que você trabalha com parâmetros (ou props, no nosso caso).

Veja o código abaixo:

```
import React from 'react';
import { Text, TouchableOpacity } from 'react-native';

const MeuBotao = ({ texto, cor }) => (
  <TouchableOpacity style={{ backgroundColor: cor }}>
    <Text>{texto}</Text>
  </TouchableOpacity>
);

export default MeuBotao;
```

Neste exemplo, temos um componente **Botão** que recebe o texto a ser exibido e a cor de fundo. Agora, suponha que você está usando esse botão em várias páginas e, em muitas delas, está passando os mesmos valores, como no exemplo abaixo:

```
// Página 1
<MeuBotao texto="Clique aqui" cor="blue" />

// Página 2
<MeuBotao texto="Clique aqui" cor="blue" />

// Página 3
<MeuBotao texto="Clique aqui" cor="blue" />

// Página 4
<MeuBotao texto="Clique aqui" cor="blue" />

// Página 5
<MeuBotao texto="Clique aqui" cor="blue" />

// Página 6
<MeuBotao texto="Clique aqui" cor="red" />
```

Perceba que, na maioria das vezes, estamos passando os mesmos valores para **texto** e **cor**. Apenas na página 6 o valor de cor muda para "red".

Então, que tal evitar essa repetição nos valores que são passados nas **props**? Para isso, vamos utilizar valores padrões.

### 2. Como definir valores padrão para props?

Uma forma simples de definir valores padrões para suas **props** é usar a propriedade `defaultProps` do componente.

Com **defaultProps**, você não precisa passar os mesmos valores o tempo todo. Se uma **prop** não for informada, o componente usará o valor padrão automaticamente.

No nosso exemplo, podemos fazer isso:

```
import React from 'react';
import { Text, TouchableOpacity } from 'react-native';

const MeuBotao = ({ texto, cor }) => (
  <TouchableOpacity style={{ backgroundColor: cor }}>
    <Text>{texto}</Text>
  </TouchableOpacity>
);

MeuBotao.defaultProps = {
  texto: 'Clique aqui',
  cor: 'blue',
};

export default MeuBotao;
```

Agora, não precisamos mais passar os mesmos valores toda vez. Se **texto** e cor **não** forem informados, o componente usará os valores definidos em `defaultProps`.

O código de uso pode ficar assim:

```
<MeuBotao />  {/* Vai usar os valores padrão */}
<MeuBotao texto="Clique aqui" cor="red" />  {/* Vai usar um valor diferente */}
```

## Vale a pena prestar atenção

As **defaultProps** são muito úteis e ajudam a evitar retrabalho. Porém, é preciso tomar cuidado com as facilidades que você utiliza na construção dos seus componentes.

Se você abusar desses recursos, pode acabar tornando a construção do seu componente mais simples, porém deixá-lo menos reutilizável.

Para você não cair nessas armadilhas, separei um conteúdo especial para você: [SOLID aplicado ao React: melhorando a modularidade e flexibilidade do código](https://www.alura.com.br/conteudo/solid-aplicado-react-melhorando-modularidade-flexibilidade-codigo).

### [Voltar ao Menu - React Native: desenvolvendo com Expo](../menu.md)
