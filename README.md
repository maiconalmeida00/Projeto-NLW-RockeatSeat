# 🎮 Assistente de Meta (Gemini + Web)

Aplicação web simples que usa a API do **Gemini** para responder dúvidas sobre **Valorant**, **League of Legends** e **CS:GO**, com foco em estratégias, builds e dicas rápidas.

---

## ✨ Funcionalidades

- Seleção de jogo: **Valorant**, **League of Legends** ou **CS:GO**  
- Campo para informar a **API KEY do Gemini**  
- Campo de pergunta livre (ex.: *“Melhor build para ADC”*)  
- Envio da pergunta para o modelo **gemini-2.5-flash**  
- Resposta:
  - Em **Markdown**, convertida para HTML com **showdown.js**
  - Curta (até ~500 caracteres)
  - Focada no meta atual do jogo
- Layout responsivo, com animações e feedback de carregamento no botão

---

## 🧱 Estrutura dos Arquivos

├── index.html **Estrutura da página**

├── style.css **Estilos e layout**

├── script.js **Lógica de integração com a API do Gemini**

└── assets/

└── logo.png **Logo exibida no cabeçalho**

---

## 🖥️ Tecnologias Utilizadas

- **HTML5**  
- **CSS3**  
- **JavaScript (Vanilla)**  
- **Google Gemini API (REST)**  
- **Showdown.js** para converter Markdown → HTML  
- **Google Fonts** (Inter, Cabin)

---

## 🚀 Como Usar

1. Obtenha uma **API KEY do Gemini** no painel do Google AI.
2. Clone ou baixe este repositório.
3. Garanta que a estrutura de pastas esteja igual à seção anterior.
4. Abra o arquivo `index.html` no navegador (pode ser com Live Server no VS Code).
5. Na página:
   - Insira sua **API KEY** no campo correspondente.
   - Selecione o jogo no **select**.
   - Escreva sua pergunta.
   - Clique em **“Perguntar”**.
6. A resposta aparecerá na área “Resposta da IA”.

---

## 🔍 Lógica do script.js

- Captura elementos do DOM:
  - `apiKey`, `gameSelect`, `questionInput`, `askButton`, `aiResponse`, `form`
- Usa `showdown.Converter()` para transformar Markdown em HTML.
- Monta um **prompt** específico para cada jogo:
  - Explica o papel do modelo (especialista em meta daquele jogo).
  - Define regras:
    - Responder só sobre o jogo escolhido.
    - Dizer **“Não sei”** se não tiver certeza.
    - Limitar tamanho da resposta.
- Envia requisição `POST` para:

https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=SUA_API_KEY

- Extrai o texto da resposta em:

data.candidates.content.parts.text

- Atualiza o HTML da `div.response-text` com o Markdown convertido.

---

## 🎨 Estilo (style.css)

- Fundo com imagem (`assets/fundo.jpg`) e gradiente nas bordas da seção.
- Tipografia com fonte **Inter**.
- Formulário responsivo com:
- `input` e `select` personalizados
- Botão com gradiente e animação de `hover`
- Animação de entrada da seção (`appear`)
- Estado de carregamento (`.loading`) com animação de `pulse`
- Caixa de resposta (`#aiResponse`) com borda lateral em destaque e texto legível.

---
