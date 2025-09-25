# ⚡️Flashy Agent⚡️

Crie seu próprio assistente de IA personalizado, sem a necessidade de código. Dê a ele uma personalidade, uma base de conhecimento e crie comandos rápidos para automatizar qualquer tarefa de texto.

Acesse o APP: https://gemini.google.com/share/6234af6cbbd8


---

## 🚀 Sobre o Projeto

**Flashy Agent** não é apenas mais uma interface de chat com IA. É um "painel de controle" completo para o poder do Google Gemini. A aplicação foi projetada para transformar a maneira como você interage com modelos de linguagem, permitindo a criação de assistentes altamente especializados para qualquer finalidade:

*   **Estudantes:** Crie um tutor que gera flashcards, resumos e explicações sobre o material da sua aula.
*   **Criadores de Conteúdo:** Desenvolva um assistente para gerar roteiros, posts para redes sociais ou ideias de artigos com um único clique.
*   **Desenvolvedores:** Tenha um parceiro de programação que gera boilerplate, explica trechos de código ou formata dados, tudo com base nas suas regras.
*   **Profissionais:** Automatize a escrita de e-mails, relatórios ou a análise de documentos.

A principal vantagem é a **persistência e personalização**. Configure uma vez e use para sempre, com todos os seus dados e preferências salvos na nuvem com o Firebase.

---

## ✨ Principais Funcionalidades

*   🧠 **Personalidade Customizável:** Defina o `prompt` principal para dar ao seu assistente uma identidade e um propósito claros.
*   📚 **Base de Conhecimento:** Forneça contexto (artigos, documentos, dados) para que a IA responda com base em informações específicas.
*   🔒 **Fatores de Persistência:** Estabeleça regras e variáveis fixas que o assistente deve sempre lembrar e aplicar.
*   🤖 **Comandos Rápidos (Macros):** Crie botões para tarefas repetitivas. Automatize qualquer prompt com um clique.
*   ☁️ **Dados Salvos na Nuvem:** Suas configurações e comandos são salvos automaticamente na sua conta usando Firebase Firestore.
*   💻 **Renderização de Código:** Blocos de código são formatados com um botão "Copiar" para facilitar o uso.
*   🎨 **Interface Intuitiva:** Um layout limpo e responsivo construído com Tailwind CSS para uma experiência de usuário agradável.

---

## 🛠️ Como Funciona? A Estrutura de 3 Passos

A interface é dividida em dois painéis principais, projetados para um fluxo de trabalho intuitivo.

<br>

| Painel Esquerdo (Configuração)                                                                                             | Painel Direito (Interação)                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
|                                                                        |                                                                                |
| **É aqui que você molda sua IA.** Defina a personalidade, adicione conhecimento e crie seus botões de automação (comandos). | **É aqui que a mágica acontece.** Converse com seu assistente personalizado e use os botões que você criou para acelerar tudo. |

<br>

### Passo 1: Defina a Base (Painel Esquerdo)
1.  **Personalidade:** Diga à IA quem ela é. Ex: `Você é um roteirista de Hollywood especialista em diálogos curtos e impactantes.`
2.  **Conhecimento:** Cole o contexto. Ex: `O resumo de um livro ou a transcrição de uma reunião.`
3.  **Fatores de Persistência:** Adicione regras fixas. Ex: `Tópico atual: Ficção Científica. Sempre use um tom sarcástico.`
4.  Clique em **"Salvar Configurações Gerais"**.

### Passo 2: Crie Atalhos (Painel Esquerdo)
1.  Dê um **Nome para o Botão**. Ex: `Criar Diálogo`
2.  Escreva o **Mini-Prompt** que ele executará. Ex: `Com base no conhecimento fornecido, crie um diálogo rápido entre dois personagens sobre o seguinte tema:`
3.  Clique em **"Adicionar Comando"**. Seu novo botão aparecerá na lista de "Comandos Salvos" e, mais importante, no painel de chat.

### Passo 3: Interaja e Automatize (Painel Direito)
1.  Seus comandos rápidos aparecem como **botões de ação** acima da caixa de texto.
2.  Clique em um botão para que seu mini-prompt seja inserido automaticamente.
3.  Adicione qualquer informação extra e envie.
4.  Converse normalmente com seu assistente, que sempre se lembrará das regras que você definiu.

---

## 🔧 Tecnologias Utilizadas

Este projeto foi construído com tecnologias modernas e eficientes, mantendo a simplicidade de um único arquivo HTML.

*   **Frontend:** HTML5, CSS3, JavaScript (ES Modules)
*   **Estilização:** [Tailwind CSS](https://tailwindcss.com/)
*   **Backend & DB:** [Firebase](https://firebase.google.com/) (Firestore para banco de dados e Authentication para usuários anônimos)
*   **Inteligência Artificial:** [Google Gemini API](https://ai.google.dev/)

---

## ⚙️ Como Rodar o Projeto Localmente

Para executar este projeto em sua máquina, você precisará configurar o Firebase e a API do Google Gemini.

### Pré-requisitos
*   Uma conta no [Google Cloud](https://cloud.google.com/) / [Firebase](https://firebase.google.com/).
*   Node.js (opcional, mas recomendado para usar um servidor local).
*   Um editor de código como o VS Code com a extensão [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).

### Passos

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/SEU_USUARIO/NOME_DO_REPOSITORIO.git
    cd NOME_DO_REPOSITORIO
    ```

2.  **Configure o Firebase:**
    *   Vá para o [Console do Firebase](https://console.firebase.google.com/) e crie um novo projeto.
    *   No painel do seu projeto, adicione um novo aplicativo Web (ícone `</>`).
    *   Copie o objeto de configuração `firebaseConfig`. Ele se parecerá com isto:
      ```javascript
      const firebaseConfig = {
        apiKey: "AIza...",
        authDomain: "seu-projeto.firebaseapp.com",
        projectId: "seu-projeto",
        storageBucket: "seu-projeto.appspot.com",
        messagingSenderId: "12345...",
        appId: "1:12345..."
      };
      ```
    *   No arquivo `index.html`, encontre a linha `const firebaseConfig = JSON.parse(...)` e **substitua-a** pelo objeto que você copiou.
    *   No menu lateral do Firebase, vá para **Authentication** -> **Sign-in method** e ative o provedor **"Anônimo"**.
    *   Vá para **Firestore Database** -> **Criar banco de dados**. Inicie no **modo de produção** e, em seguida, vá para a aba **"Regras"** e altere para permitir leitura/escrita para usuários autenticados (para testes):
      ```json
      rules_version = '2';
      service cloud.firestore {
        match /databases/{database}/documents {
          match /{document=**} {
            allow read, write: if request.auth != null;
          }
        }
      }
      ```

3.  **Configure a API do Google Gemini:**
    *   Vá para o [Google AI Studio](https://aistudio.google.com/).
    *   Clique em **"Get API key"** e crie uma nova chave de API.
    *   No arquivo `index.html`, encontre a linha:
      ```javascript
      const apiKey = ""; // Deixe em branco
      ```
    *   **Cole sua chave de API** dentro das aspas:
      ```javascript
      const apiKey = "SUA_API_KEY_AQUI";
      ```
    > ⚠️ **Atenção:** Nunca exponha sua chave de API em um repositório público. Para um projeto real, use variáveis de ambiente ou um backend para gerenciar a chave de forma segura.

4.  **Execute o projeto:**
    *   Abra o arquivo `index.html` no VS Code.
    *   Clique com o botão direito e selecione **"Open with Live Server"**.
    *   Seu navegador abrirá com o Flashy Agent funcionando!

---

## 🤝 Contribuição

Contribuições são o que tornam a comunidade de código aberto um lugar incrível para aprender, inspirar e criar. Qualquer contribuição que você fizer será **muito apreciada**.

1.  Faça um Fork do projeto
2.  Crie sua Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Faça o Commit de suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4.  Faça o Push para a Branch (`git push origin feature/AmazingFeature`)
5.  Abra um Pull Request

---

## 📜 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.
