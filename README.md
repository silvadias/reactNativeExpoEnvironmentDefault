# React Native Environment with Docker and Expo - Initial Project Setup

Este é um guia passo a passo para configurar um ambiente React Native com Docker e Expo.

## Passo a Passo para Configurar o Ambiente

1. **Clone o projeto**
   ```bash
   sudo git clone git@github.com:silvadias/reactNativeExpoEnvironmentDefault.git
   ```

2. **Execute o Docker Compose**
   ```bash
   sudo docker-compose up -d
   ```

3. **Acesse o contêiner do React Native**
   ```bash
   sudo docker exec -it reactExpo sh
   ```

4. **Inicie o servidor Expo**
   ```bash
   npx expo start --tunnel
   ```

5. **Instale o aplicativo Expo Go**
   - Baixe o **Expo Go** na [Google Play Store](https://play.google.com) (para Android) ou na [App Store](https://www.apple.com/app-store/) (para iOS).

6. **Escaneie o código QR**
   - Escaneie o código QR exibido no terminal usando o aplicativo Expo Go.

7. **Desenvolva seu projeto React Native com Expo**
   - Agora você está pronto para começar a desenvolver seu projeto React Native com Expo.
