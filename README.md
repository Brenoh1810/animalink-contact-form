# 🎓 Trabalho Acadêmico: Formulário de Contato Inteligente — AnimaLink

Este repositório contém o componente de formulário de contato desenvolvido como parte de um **projeto acadêmico integrado** para a startup fictícia **AnimaLink** (uma plataforma de IA voltada para a saúde mental e enriquecimento cognitivo de pets). 

Enquanto a proposta de negócio e a interface principal (Landing Page) foram estruturadas na ferramenta Gamma App, este repositório hospeda a implementação técnica, funcional e isolada do formulário de captura de leads com integrações multiplas de APIs.

---

## 📌 Contexto do Projeto

O objetivo do trabalho foi unir conceitos de **UX Writing**, **Front-end Avançado** e **Consumo de APIs Públicas** para resolver uma dor real de mercado: a ansiedade de separação em animais de estimação e a culpa dos tutores urbanos. 

O formulário foi totalmente estilizado com a identidade visual da marca (**"Serenidade Digital"**), consome serviços externos em tempo real e armazena os dados de forma assíncrona, alimentando um banco de dados integrado no Google Sheets através do Google Forms.

---

## 🛠️ Tecnologias e Conceitos Utilizados

- **HTML5 Semântico:** Estruturação de dados estruturados, validações nativas e acessibilidade em formulários.
- **CSS3 Avançado:** Estilização baseada em variáveis (`:root`), layouts responsivos com Flexbox, tratamento de estados de inputs (`:focus`, `:disabled`) e animações de interface (Keyframes para o *loader*).
- **JavaScript (Vanilla ES6+):** - Manipulação assíncrona do DOM.
  - Controle de eventos de interface (`submit`, `input`, `blur`).
  - Expressões Regulares (Regex) para validações estritas de e-mail e tratamento de dados.
- **Comunicação Assíncrona (AJAX/Fetch API):** Requisições baseadas em `Promises` utilizando métodos `GET` e `POST` para troca de dados em segundo plano sem recarregamento de página.

---

## 🔌 APIs Públicas Integradas

O projeto consome de forma simultânea e sem chaves privadas (cumprindo os requisitos de segurança em ambientes de código aberto destacados em aula) os seguintes serviços externos:

1. **API ViaCEP (Funcional / Lógica de Negócio):** - Ao disparar o evento `blur` (sair do campo) no input de CEP, o JavaScript realiza uma busca assíncrona na URL `https://viacep.com.br/ws/`.
   - Retorna os dados de endereço e realiza o **autopreenchimento** automático dos campos de *Cidade* e *UF*, bloqueando-os para edição a fim de mitigar erros de digitação e redundância de dados.
2. **Dog CEO API (Experiência do Usuário / Mídia Dinâmica):**
   - Consome o endpoint `https://dog.ceo/api/breeds/image/random` para retornar e injetar na interface uma imagem ou GIF aleatório de um pet a cada carregamento da página ou clique no botão de atualização, trazendo um componente de descontração e engajamento para a UI.
3. **Google Forms API (Persistência / Banco de Dados):**
   - Recebe todas as informações validadas no front-end em modo shadow (`no-cors`), injetando os dados diretamente no endpoint `/formResponse` para armazenamento e triagem automatizada de leads.
     
---

## ⚙️ Como Configurar a Integração

Para fins de avaliação ou replicação do projeto acadêmico, o fluxo de dados é estruturado em 3 etapas:

1. **Mapeamento de Inputs:** Os códigos identificadores de campo (`entry.XXXXX`) são extraídos através da opção *"Gerar link preenchido automaticamente"* no painel de edição de um formulário do Google Forms (incluindo os campos de CEP e Localização).
2. **Substituição no JavaScript:** Os IDs reais devem ser inseridos no objeto do script:
   ```javascript
   const GOOGLE_ENTRIES = {
       name: 'entry.SEU_ID_AQUI',
       email: 'entry.SEU_ID_AQUI',
       phone: 'entry.SEU_ID_AQUI',
       message: 'entry.SEU_ID_AQUI',
       cep: 'entry.SEU_ID_AQUI',
       location: 'entry.SEU_ID_AQUI'
   };
