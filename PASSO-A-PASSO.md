# App Coleta de Água — passo a passo para publicar

Arquivos desta pasta:
- `index.html`: o aplicativo completo.
- `firestore.rules`: as regras de segurança do banco de dados.

Tudo roda no plano gratuito do Firebase (Spark). Faça os passos **no computador**. Leva cerca de 20 minutos.

---

## 1. Criar o projeto no Firebase
1. Acesse **console.firebase.google.com** e entre com sua conta Google (Gmail).
2. Clique em **Criar projeto** e dê um nome, por exemplo `coleta-agua`.
3. O Google Analytics pode ser desativado. Conclua a criação.

## 2. Ativar o login (e-mail/senha e Google)
1. No menu, abra **Authentication** e clique em **Vamos começar**.
2. Na aba **Método de login**, escolha **E-mail/senha**, ative a primeira opção e salve.
3. Clique em **Adicionar novo provedor**, escolha **Google**, ative, selecione seu e-mail em **E-mail de suporte do projeto** e salve.

## 3. Criar o banco de dados
1. No menu, abra **Firestore Database** e clique em **Criar banco de dados**.
2. Para a localização, escolha **southamerica-east1 (São Paulo)**.
3. Escolha **Iniciar no modo de produção** e conclua.

## 4. Colar as regras de segurança
1. Ainda no Firestore, abra a aba **Regras**.
2. Apague o conteúdo e cole todo o arquivo `firestore.rules`.
3. Troque `seuemail@gmail.com` pelo **seu e-mail de administrador**.
4. Clique em **Publicar**.

## 5. Ligar o app ao seu projeto
1. Clique na engrenagem ⚙️ e depois em **Configurações do projeto**.
2. Em **Seus apps**, clique no ícone **Web `</>`**, dê um apelido (ex.: `coleta-web`) e registre. Não precisa marcar o Hosting.
3. O Firebase mostra um bloco `firebaseConfig`. Copie os valores de `apiKey`, `authDomain`, `projectId` e `appId`.
4. Abra o `index.html` em um editor de texto, como o Bloco de Notas ou o TextEdit. Logo no começo do código, onde está **CONFIGURAÇÃO**:
   - substitua cada `COLE_AQUI` pelo valor correspondente;
   - em `ADMIN_EMAILS`, troque `seuemail@gmail.com` pelo mesmo e-mail do passo 4.
5. Salve o arquivo.

> A `apiKey` do Firebase pode ficar visível no arquivo; isso é normal. Quem protege os dados são as regras do passo 4.

## 6. Colocar o app no ar (Netlify, gratuito)
1. Acesse **app.netlify.com/drop**.
2. Arraste a **pasta** com o `index.html` para a página.
3. Crie uma conta gratuita para o site não ser apagado. O Netlify mostra o endereço, algo como `nome-aleatorio.netlify.app`. Em **Site configuration → Change site name** você pode trocar para `coleta-agua.netlify.app`, por exemplo.

## 7. Autorizar o endereço no Firebase
1. No Firebase, abra **Authentication → Configurações → Domínios autorizados**.
2. Clique em **Adicionar domínio** e cole o endereço do Netlify, sem `https://` (ex.: `coleta-agua.netlify.app`).

## 8. Primeiro acesso (administrador)
1. Abra o endereço do app e toque em **Criar cadastro** usando o **e-mail de administrador**.
2. Confirme o e-mail pelo link que chega na caixa de entrada. Confira também o spam.
3. No app, toque em **Sair** e **entre de novo**. Agora você é o administrador.

## 9. Convidar a equipe
1. Envie o link do app para a equipe (Karbela, Bruna, Josenilson, Fátima…).
2. Cada pessoa entra com o botão **Entrar com Google** ou cria um cadastro com o e-mail pessoal e uma senha.
3. Em **Equipe → Aguardando aprovação**, toque em **Aprovar**. Use **Tornar admin** para dar à Karbela as mesmas permissões que você.

---

## Observações
- **Laudos:** cole o link do arquivo no Google Drive (compartilhado com "qualquer pessoa com o link"). Assim o app não precisa de armazenamento pago.
- **Esqueci a senha:** a própria tela de login tem a opção de receber um link de recuperação por e-mail.
- **Atualizar o app depois:** edite o `index.html` e arraste a pasta de novo no Netlify, em **Deploys**. Os dados continuam no Firebase.
