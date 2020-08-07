# Projeto Mobile

## Iniciando o projeto Mobile

- Instalar o Expo `npm install -g expo-cli`
- Criar o projeto Mobile `expo init mobile`
- Selecionar o template `blank (TypeScript)`
- Iniciar o projeto Mobile `yarn start`

## Particularidades do React Native

- Mesmos conceitos de componentes e JSX
- React Native não utiliza tags HTML, ele utilizada componentes do pacote `react-native`
- React Native utiliza `View` no lugar de divs, sections...
- React Native utiliza `Text` no lugar de tags de texto
- React Native não existe estilos `classes, id, ou arquivos css`, ele utiliza o StyleSheet do pacote `react-native`
- React Native não existe herança de estilos, é necessário escrever estilos para cada elemento (somente o `Text` realizar herança de estilos)
- No React Native as propriedades do StyleSheet são escritas em json/js, no css existe a separação por hífem, no StyleSheet não tem o hífem, e a primeira letra após o hífem é maiúscula
- No React Native não tem as propriedades do css: animações, gradientes, grid
- No React Native todos os elementos já tem display flex
- No React Native o padrão do flexDirection é collumn
- O React Native não trabalha diretamente com svg, para conseguir é necessário usar uma lib.
- O React Native não trabalha com as variáveis do css

### Ajustando os arquivos do projeto

- Criar as pastas
  - src
  - src/assets
  - src/assets/images
  - src/assets/images/icons
  - src/pages
  - src/pages/Landing
- Criar os arquivos
  - src/pages/Landing/index.tsx
  - src/pages/Landing/styles.ts

### Resolvendo png dentro do React Native

- Por padrão o Typescript não consegue entender quando usando png, por isso, criamos uma pasta de tipos
- Criar a pasta/arquivos src/@types/index.d.ts
- Adicionar o conteúdo `declare module '*.png';`

### Inserindo o pacote de fontes

- Instalar as fontes `expo install expo-font @expo-google-fonts/archivo @expo-google-fonts/poppins`
- Alterar o arquivo `App.tsx` para incluir o carregamento das fontes

```javascript
import { StatusBar } from 'expo-status-bar';
import React from 'react';
import { AppLoading } from 'expo';

import { Archivo_400Regular, Archivo_700Bold, useFonts } from '@expo-google-fonts/archivo';
import { Poppins_400Regular, Poppins_600SemiBold } from '@expo-google-fonts/poppins';

import Landing from './src/pages/Landing';

export default function App() {
  let [ fontsLoaded ] = useFonts({
    Archivo_400Regular,
    Archivo_700Bold,
    Poppins_400Regular,
    Poppins_600SemiBold,
  });

  if (!fontsLoaded) {
    return <AppLoading />;
  } else {
    return (
      <>
        <Landing />
        <StatusBar style="auto" />
      </>
    );
  }
}
```

### Navegação na aplicação

- Instalar o react-navigation `yarn add @react-navigation/native`
- Instalar as dependências para o Expo `expo install react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view`
- Instalar o react-navigation/stack (navegação em pilha - página vai e volta) `yarn add @react-navigation/stack`
- Instalar o react-navigation/bottom-tabs (navegação em abas - na mesma página) `yarn add @react-navigation/bottom-tabs`
- Criar a pasta/arquivo src/routes/AppStack.tsx
- Definir a navegação no arquivo AppStack.tsx
- Inserir o componente de navegação AppStack no arquivo App.tsx

### Criando as outras telas da aplicação

- Criar as pastas/arquivos
  - src/pages/GiveClasses/index.tsx
  - src/pages/GiveClasses/styles.ts
  - src/pages/Favorites/index.tsx
  - src/pages/Favorites/styles.ts
  - src/pages/TeacherList/index.tsx
  - src/pages/TeacherList/styles.ts

### Navegação em abas na aplicação e alteração no AppStack.tsx

- Criar a pasta/arquivo src/routes/StudyTabs.tsx
- Definir a navegação no arquivo StudyTabs.tsx para os componentes `Favorites` e `TeacherList`
- Alterar o arquivo AppStack.tsx para incluir a navegação até o componente de abas `<Screen name="Study" component={StudyTabs} />`
- Alterar a Landing para incluir as rotas

```javascript
// ... trecho de código omitido

import { useNavigation } from '@react-navigation/native';
function Landing() {
  const { navigate } = useNavigation();

  function handleNavigationToClassesPage() {
    navigate('GiveClasses');
  }

  function handleNavigationToStudyPage() {
    navigate('Study');
  }

  return (
    // ... trecho de código omitido
    <RectButton
      onPress={handleNavigationToStudyPage}
      style={[styles.button, styles.buttonPrimary]}
    >
      <Image source={studyIcon} />
      <Text style={styles.buttonText}>Estudar</Text>
    </RectButton>
    // ... trecho de código omitido
  );
}

export default Landing;
```