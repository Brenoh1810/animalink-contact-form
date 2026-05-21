# 🐾 AnimaLink - Formulário de Contato Inteligente com Integração Google Forms

Este é um componente de formulário de contato robusto, responsivo e minimalista, desenvolvido sob medida para a landing page da **AnimaLink** (plataforma de IA para saúde mental e enriquecimento cognitivo de pets). 

O formulário utiliza a paleta de cores institucional **"Serenidade Digital"** da marca (Branco Gelo, Azul Profundo e Lavanda Suave) e conta com um sistema de envio 100% oculto e assíncrono conectado diretamente ao **Google Forms/Google Sheets**.

---

## ✨ Funcionalidades

- **Validação Avançada com UX Writing:** Validação rigorosa via JavaScript que impede o envio de campos vazios, e-mails com formatos inválidos ou sequências aleatórias.
- **Máscara de Telefone em Tempo Real:** Captura os dígitos inseridos e formata automaticamente no padrão `(DD) 99999-9999`, impedindo a inserção de letras ou caracteres especiais.
- **Feedback Visual Elegante (UI/UX):** Campos inválidos recebem instantaneamente um destaque visual suave em tom de alerta (terracota sutil) e mensagens de erro descritivas.
- **Botão Inteligente com Loader (Estado de Envio):** O botão de envio exibe um indicador de carregamento (*spinner* animado) e entra em estado desativado (`disabled`) durante a transmissão para evitar cliques duplicados.
- **Integração Oculta (Modo Shadow/AJAX):** Utiliza a API `fetch` com modo `no-cors` para enviar os dados para o endpoint `/formResponse` do Google Forms. O usuário permanece no site sem redirecionamentos ou uso de iframes.

---

## 🎨 Paleta de Cores Aplicada (CSS Variables)

- `Branco Gelo (#F8FAFF)`: Fundo da página, trazendo leveza e modernidade.
- `Azul Profundo (#1A2B4C)`: Cor principal de textos e títulos, transmitindo autoridade tecnológica.
- `Lavanda Suave / Roxo Moderno (#6C63FF)`: Cor de destaque para botões, focos de inputs e interações primárias.
- `Alerta Terracota (#E29578)`: Utilizado pontualmente para destacar erros e validações sem quebrar a harmonia visual.

---

## 🛠️ Como Configurar a Integração com o Google Forms

Para ativar o recebimento automático de dados na sua planilha do Google, siga estes 3 passos:

1. **Mapeie os IDs das Perguntas:**
   - No painel de edição do seu Google Forms, clique nos três pontos (canto superior direito) e selecione **"Gerar link preenchido automaticamente"**.
   - Digite respostas fáceis de identificar em cada campo (ex: `NOMEDISP`, `EMAILDISP`) e clique em **"Gerar link"**.
   - No link copiado, identifique os códigos de entrada de cada campo, que se parecem com: `entry.1111111111`.

2. **Substitua no Código JavaScript:**
   - Abra o arquivo de código do formulário e localize o objeto `GOOGLE_ENTRIES`.
   - Substitua os códigos fictícios pelos IDs reais gerados pelo seu formulário:
     ```javascript
     const GOOGLE_ENTRIES = {
         name: 'entry.SEU_ID_AQUI',
         email: 'entry.SEU_ID_AQUI',
         phone: 'entry.SEU_ID_AQUI',
         message: 'entry.SEU_ID_AQUI'
     };
     ```

3. **Configure a URL de Recebimento:**
   - Pegue a URL inicial do seu formulário (até o ID longo) e certifique-se de que ela termina com `/formResponse` em vez de `/viewform`. Substitua na constante:
     ```javascript
     const GOOGLE_FORMS_URL = 'https://docs.google.com/forms/d/e/SEU_ID_LONGO_DO_FORMULARIO/formResponse';
     ```

---

## 📊 Como Aceder às Respostas

1. Abra o seu **Google Forms**.
2. Vá até a aba **"Respostas"** para ver a listagem de leads em tempo real e gráficos estatísticos.
3. Para uma gestão profissional, clique no ícone verde de **Criar Planilha** (Google Sheets). Uma planilha vinculada será gerada automaticamente, onde cada novo contacto do site criará uma nova linha organizada com data e hora.

---

## 📁 Estrutura do Ficheiro

O componente foi estruturado em um único ficheiro auto-contido para facilitar a portabilidade:
- **HTML5:** Estrutura semântica dos campos de entrada.
- **CSS3:** Estilização baseada em variáveis, efeitos de transição e animação do *loader*.
- **JavaScript (Vanilla):** Lógica de comportamento, máscaras dinâmicas, validação e requisições à API.

---
Desenvolvido com foco em performance, acessibilidade e conversão para o ecossistema **AnimaLink** 🐾.
