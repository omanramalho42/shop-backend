# Documentação de Configuração do Back-End da Aplicação

Esta documentação descreve os passos necessários para configurar e executar o back-end de uma aplicação com base no arquivo `.env` e no arquivo `package.json` fornecidos.

## Requisitos Prévios

Antes de começar, certifique-se de que você possui os seguintes requisitos prévios instalados em seu sistema:

1. **Node.js e npm:** Certifique-se de ter o Node.js e o npm (Node Package Manager) instalados em seu sistema. Você pode baixá-los em [nodejs.org](https://nodejs.org/).

2. **MongoDB:** Certifique-se de ter um servidor MongoDB em execução ou configure um serviço MongoDB na nuvem, conforme necessário.

## Configuração do Back-End

Siga os passos abaixo para configurar e executar o back-end da aplicação:

1. **Clonar o Repositório:** Clone o repositório da aplicação para o seu sistema, se ainda não o tiver feito.

   ```bash
   git clone <URL_DO_REPOSITÓRIO>
   ```

2. **Navegar para a Pasta do Back-End:** Mude para o diretório do back-end da aplicação.

   ```bash
   cd backend
   ```

3. **Instalar Dependências:** Execute o seguinte comando para instalar as dependências listadas no arquivo `package.json`.

   ```bash
   npm install
   ```

4. **Configurar Variáveis de Ambiente:**

   Crie um arquivo `.env` na raiz do diretório do back-end (se já não existir) e defina as variáveis de ambiente necessárias. No seu caso, o arquivo `.env` já foi fornecido com a seguinte configuração:

   ```plaintext
   PORT=3001
   JWT_SECRET=secret
   MONGODB_URI=your_secret_token_mongo_db
   PAYPAL_CLIENT_ID=your_secret_token
   ```

   - `PORT`: A porta em que o servidor do back-end será executado.
   - `JWT_SECRET`: A chave secreta usada para assinar tokens JWT.
   - `MONGODB_URI`: A URI de conexão com o banco de dados MongoDB.
   - `PAYPAL_CLIENT_ID`: O ID do cliente PayPal para integração de pagamento.

5. **Executar o Back-End:**

   Você pode iniciar o servidor do back-end com os seguintes comandos:

   - Para ambiente de desenvolvimento com reinicialização automática (usando nodemon):

     ```bash
     npm run dev
     ```

   - Para ambiente de produção:

     ```bash
     npm run start
     ```

   Certifique-se de que o servidor esteja em execução na porta especificada no arquivo `.env`.

## Scripts Personalizados

O arquivo `package.json` inclui alguns scripts personalizados que podem ser úteis durante o desenvolvimento:

- `npm run dev`: Inicia o servidor do back-end em modo de desenvolvimento com reinicialização automática usando o nodemon.
- `npm run start`: Inicia o servidor do back-end em modo de produção.
- `npm test`: Executa testes unitários da aplicação.

## Conclusão

Com esses passos, você deverá ter configurado e executado com sucesso o back-end da aplicação. Certifique-se de que o front-end da aplicação esteja configurado corretamente para se comunicar com o back-end. Para quaisquer problemas ou dúvidas adicionais, consulte a documentação da aplicação ou entre em contato com a equipe de desenvolvimento.

# Configuração do Back-End da Aplicação

Esta documentação fornece instruções adicionais sobre como configurar o back-end da aplicação, incluindo a criação de tokens na API do PayPal e a configuração do MongoDB.

## Criação de Token na API do PayPal

Para configurar a integração com o PayPal e criar um token de acesso, siga estas etapas:

1. Acesse o [Portal de Desenvolvedores do PayPal](https://developer.paypal.com/).

2. Faça login na sua conta de desenvolvedor do PayPal ou crie uma, se ainda não tiver uma.

3. No painel de controle, crie um novo aplicativo para a sua aplicação:

   - Clique em "My Apps & Credentials" (Meus Apps e Credenciais).
   - Em "REST API apps" (Apps de API REST), clique em "Create App" (Criar Aplicativo).
   - Siga as instruções para criar o aplicativo, fornecendo informações como nome, descrição e ambiente (sandbox ou produção).

4. Após criar o aplicativo, você receberá um Client ID (ID do Cliente) e um Secret (Segredo). Essas credenciais são usadas para autenticar sua aplicação com a API do PayPal.

5. Certifique-se de que o Client ID seja adicionado à variável de ambiente `PAYPAL_CLIENT_ID` no arquivo `.env` do seu back-end, conforme mencionado anteriormente na documentação.

6. Agora você pode usar o Client ID para autenticar sua aplicação e realizar transações de pagamento com o PayPal.

## Configuração do MongoDB

Para configurar o MongoDB, você já possui a URI de conexão definida na variável de ambiente `MONGODB_URI` no arquivo `.env`. No entanto, aqui estão algumas etapas adicionais para configurar o MongoDB, se necessário:

1. Certifique-se de ter o MongoDB instalado em seu sistema ou use um serviço de hospedagem na nuvem, como o MongoDB Atlas.

2. Caso esteja usando o MongoDB localmente, inicie o servidor MongoDB com o seguinte comando:

   ```bash
   mongod
   ```

3. Certifique-se de que a URI de conexão no arquivo `.env` esteja corretamente formatada e que inclua as informações necessárias para se conectar ao seu banco de dados MongoDB.

4. Teste a conexão com o banco de dados executando seu servidor Node.js. Se tudo estiver configurado corretamente, a aplicação se conectará ao banco de dados MongoDB usando a URI definida.

## Conclusão

Com estas instruções adicionais, você configurou a integração com o PayPal e configurou o MongoDB para o back-end da aplicação. Lembre-se de manter suas credenciais do PayPal em segurança e não compartilhá-las publicamente. Para quaisquer problemas ou dúvidas adicionais, consulte a documentação da API do PayPal e a documentação do MongoDB, ou entre em contato com a equipe de desenvolvimento.
