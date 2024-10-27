
# Ambiente de Desenvolvimento React Native com Expo e Docker

Este guia fornece as instruções para configurar e rodar um ambiente de desenvolvimento React Native usando Expo e Docker. Siga as etapas abaixo para iniciar seu projeto.

---

### 1. Instalação do Docker

Primeiro, instale o Docker no sistema. Execute os comandos abaixo para instalação via linha de comando:

```bash
# Atualizar pacotes
sudo apt update

# Instalar pacotes necessários
sudo apt install apt-transport-https ca-certificates curl software-properties-common

# Adicionar chave GPG do Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Adicionar repositório do Docker
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Instalar o Docker
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
```

---

### 2. Instalação do Docker Compose

Em seguida, instale o Docker Compose para gerenciar contêineres com mais facilidade:

```bash
# Baixar versão do Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

# Permissão de execução
sudo chmod +x /usr/local/bin/docker-compose

# Verificar instalação
docker-compose --version
```

---

### 3. Clonar o Repositório do Projeto

Clone o projeto React Native com o ambiente Docker configurado usando o comando abaixo:

```bash
git clone https://github.com/silvadias/reactNativeExpoEnvironmentDefault
cd reactNativeExpoEnvironmentDefault
```

---

### 4. Subir o Contêiner

Com o Docker e o Docker Compose configurados, suba o contêiner executando o comando:

```bash
docker-compose up -d
```

---

### 5. Entrar no Contêiner `nodeExpo`

Após subir o contêiner, entre no contêiner `nodeExpo` para acessar o ambiente de desenvolvimento:

```bash
docker exec -it nodeExpo bash
```

---

### 6. Iniciar o Expo com Tunnel

Dentro do contêiner, execute o comando abaixo para iniciar o Expo e gerar o QR code:

```bash
npx expo start --tunnel
```

O Expo será iniciado, e um QR code será exibido no terminal. Esse QR code permitirá que você teste o aplicativo diretamente em um dispositivo físico.

---

### 7. QR Code e Acesso pelo Navegador

- O projeto estará disponível em uma página web no endereço `localhost:8081`. Acesse-o para verificar o status do Expo.
- Para testar no celular, utilize o QR code gerado no terminal.

---

### 8. Instalação do Aplicativo Expo Go

Para visualizar o projeto em um dispositivo físico, instale o aplicativo **Expo Go** no seu dispositivo (disponível na Play Store e App Store).

---

### 9. Escaneie o QR Code

Abra o aplicativo **Expo Go** no seu dispositivo e escaneie o QR code gerado no terminal. Isso permitirá que você visualize e interaja com o projeto diretamente no dispositivo.

---

Agora, seu ambiente Expo está pronto! Basta iniciar suas atividades de desenvolvimento no React Native utilizando o Expo.
