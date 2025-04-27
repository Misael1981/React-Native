# npx expo install

Um "cara" importante no processo de construção de qualquer aplicativo: o **gerenciador de pacotes**.

Gerenciadores de pacotes são ferramentas que facilitam a instalação de bibliotecas e dependências no seu projeto. Você já conhece o npm; é por ele que vamos começar o papo de hoje.

## 1. npm install

O npm (Node Package Manager) é um dos gerenciadores de pacotes mais populares, principalmente em projetos Node.js, como o React Native.

Para instalar uma biblioteca usando o npm, basta rodar:

```
npm install nome-da-lib
```

Mas calma aí, se fosse só sobre o comando npm install, não estaríamos aqui, certo?

A verdade é que, quando estamos lidando com projetos React Native que utilizam o Expo, existe uma forma diferente de instalar pacotes: o `npx expo install`.

## 2. `npx expo install

O comando `npx expo install` funciona de maneira semelhante ao `npm install`, mas foi pensado especificamente para projetos com Expo:

```
npx expo install nome-da-lib
```

A grande vantagem desse comando é que ele **verifica automaticamente se a versão da biblioteca é compatível com o Expo SDK que você está usando**. Isso evita problemas de compatibilidade e dores de cabeça com pacotes que podem não funcionar direito no seu projeto.

O `expo install` também configura automaticamente o seu projeto, especialmente quando o pacote exige alguma configuração nativa, que o Expo chama de ["autolinking"](https://docs.expo.dev/modules/autolinking/).

## 3. Qual utilizar?

Então, qual comando escolher?

- Sempre que estiver em um projeto **React Native** com Expo, use `npx expo install`. Ele facilita a configuração e evita problemas de compatibilidade;
- Se a biblioteca que você precisa não estiver disponível via Expo (ou estiver em fase beta), aí sim o `npm install` pode ser uma alternativa.

No fim das contas, o **Expo foi feito para facilitar a sua vida**, então aproveite essas vantagens sempre que possível.

### [Voltar ao Menu - React Native: desenvolvendo com Expo](../menu.md)
