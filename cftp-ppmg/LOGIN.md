# Ativar o login com Google (Firebase)

O site já tem a tela de login pronta. Ela só aparece depois que o arquivo
`firebase-config.js` recebe a configuração de um projeto Firebase.

1. Entre em https://console.firebase.google.com com uma conta Google e clique em
   **Criar projeto** (pode desativar o Google Analytics).
2. **Authentication → Vamos começar → Google → Ativar**, escolha o e-mail de
   suporte e clique em **Salvar**.
3. **Authentication → Configurações → Domínios autorizados → Adicionar domínio:**
   `cftp2026-hash.github.io`
4. **Firestore Database → Criar banco de dados** (local `southamerica-east1`,
   modo de produção). Na aba **Regras**, cole o conteúdo de `firestore.rules`
   e clique em **Publicar**.
5. **Configurações do projeto (engrenagem) → Seus apps → ícone `</>`** (App da Web),
   dê um nome e registre. Copie o objeto `firebaseConfig` que aparece.
6. Em `firebase-config.js`, troque `null` pelo objeto copiado, por exemplo:

   ```js
   window.FIREBASE_CONFIG = {
     apiKey: "AIza...",
     authDomain: "seu-projeto.firebaseapp.com",
     projectId: "seu-projeto",
     storageBucket: "seu-projeto.appspot.com",
     messagingSenderId: "123...",
     appId: "1:123...:web:abc..."
   };
   ```

Esses dados não são secretos: o Firebase foi feito para eles ficarem no site.
Quem protege o progresso de cada pessoa são as regras do passo 4.

Para ver quem entrou ou desativar uma conta: **Authentication → Usuários**.
