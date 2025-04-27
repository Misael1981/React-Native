# CSS vs StyleSheet

No React Native, a estilização segue uma abordagem diferente do CSS normal que já estamos acostumados. Aqui, utilizamos objetos JavaScript para definir os estilos.

Até agora, vimos que podemos aplicar esses estilos `inline`, passando pela prop `style` ou podemos utilizar o `StyleSheet.create`, deixando o estilo separado do JSX e organizando melhor o nosso código.

```
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

const App = () => {
  return (
    <View style={styles.container}>
      <Text style={styles.text}>Um mago nunca se atrasa, nem se adianta. Ele chega exatamente quando pretende chegar.</Text>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f0f0f0',
  },
  text: {
    fontSize: 20,
    color: '#333',
  },
});

export default App;
```

Este código cria um componente que exibe uma frase centralizada na tela. Os estilos são definidos usando o `StyleSheet` para configurar o layout e a aparência, da mesma forma que fizemos em aula

Perceba que existe uma certa semelhança nas propriedades do nosso `StyleSheet` com propriedades CSS, mas não são iguais!

## CSS x StyleSheet

Dá para listar três diferenças principais entre o CSS e o styleSheet do React Native!

### 1) Nome das propriedades

No React Native, usamos camelCase no lugar de kebab-case. Por exemplo: `background-color` vira `backgroundColor`.

### 2) Sem classes ou IDs

Em vez de definir classes ou IDs, aplicamos os estilos diretamente nos componentes usando a propriedade `style`.

### 3) Flexbox por padrão

No React Native, o layout é gerenciado automaticamente pelo Flexbox (sendo a direção padrão `column` ao invés de `row`, como na web), o que simplifica bastante o posicionamento dos elementos.

### [Voltar ao Menu - React Native: desenvolvendo com Expo](../menu.md)
