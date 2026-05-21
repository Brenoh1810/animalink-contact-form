# 🎓 Trabalho Acadêmico: Formulário de Contato Inteligente — AnimaLink

Este repositório contém o componente de formulário de contato desenvolvido como parte de um **projeto acadêmico integrado** para a startup fictícia **AnimaLink** (uma plataforma de IA voltada para a saúde mental e enriquecimento cognitivo de pets). 

Enquanto a proposta de negócio e a interface principal (Landing Page) foram estruturadas na ferramenta Gamma App, este repositório hospeda a implementação técnica, funcional e isolada do formulário de captura de leads.

---

## 📌 Contexto do Projeto

O objetivo do trabalho foi unir conceitos de **UX Writing**, **Front-end (HTML5/CSS3/JavaScript)** e **Integração de Sistemas** para resolver uma dor real de mercado: a ansiedade de separação em animais de estimação e a culpa dos tutores urbanos. 

O formulário foi totalmente estilizado com a identidade visual da marca (**"Serenidade Digital"**) e programado para coletar dados de forma assíncrona, alimentando um banco de dados integrado no Google Sheets através do Google Forms.

---

## ✨ Funcionalidades Técnicas Implementadas

- **Validação Avançada de Dados:** Scripts em JavaScript que impedem o envio de dados falsos, e-mails estruturalmente inválidos ou campos em branco, aplicando conceitos de UX para guiar o usuário.
- **Máscara Dinâmica de Telefone:** Filtro em tempo real que aceita apenas números e aplica automaticamente a formatação `(DD) 99999-9999`, bloqueando letras e caracteres especiais.
- **Feedback Visual de UI/UX:** Alertas visuais sofisticados usando variáveis CSS. Os campos incorretos ganham destaque em tom terracota suave (alerta funcional) sem quebrar a estética minimalista.
- **Gerenciamento de Estado do Botão (Loader):** Mecanismo que desativa o botão de envio (`disabled`) e exibe um *spinner* animado por CSS durante a transmissão, evitando requisições duplicadas.
- **Integração Oculta com Google Forms (AJAX/Fetch):** Envio de dados em segundo plano utilizando a API `fetch` com modo `no-cors` voltado para o endpoint `/formResponse`. O usuário conclui o fluxo sem ser redirecionado para páginas externas do Google.

---

## 🎨 Paleta de Cores Institucional (CSS Variables)

- `Branco Gelo (#F8FAFF)`: Fundo sutil que transmite leveza, limpeza e modernidade.
- `Azul Profundo (#1A2B4C)`: Tipografia principal e títulos, trazendo o peso da autoridade tecnológica.
- `Lavanda Suave / Roxo Moderno (#6C63FF)`: Pontos de conversão, foco de inputs e interações de destaque.
- `Alerta Terracota (#E29578)`: Tratamento estético focado em acessibilidade e indicação de erros de preenchimento.

---

## 🛠️ Como Funciona a Configuração da Integração

Para fins de avaliação ou replicação do projeto acadêmico, o fluxo de dados é estruturado em 3 etapas:

1. **Mapeamento de Inputs:** Os códigos identificadores de campo (`entry.XXXXX`) são extraídos através da opção *"Gerar link preenchido automaticamente"* no painel de edição de um formulário do Google Forms.
2. **Substituição no JavaScript:** Os IDs reais devem ser inseridos no objeto do script:
   ```javascript
   const GOOGLE_ENTRIES = {
       name: 'entry.SEU_ID_AQUI',
       email: 'entry.SEU_ID_AQUI',
       phone: 'entry.SEU_ID_AQUI',
       message: 'entry.SEU_ID_AQUI'
   };
