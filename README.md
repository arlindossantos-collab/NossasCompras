# 🛒 Nossas Compras — Documentação Técnica (v2.4.0)

Aplicação Web Single-Page (SPA) progressiva, colaborativa e responsiva, desenvolvida para gerenciar listas de compras do casal/família em tempo real, com suporte a múltiplos estabelecimentos, assistente de voz e categorização avançada.

---

## 🛠️ 1. Arquitetura e Tecnologias

- **Frontend:** HTML5, JavaScript ES6+ (Módulos nativos), CSS3 com Tailwind CSS (via CDN).
- **Ícones:** FontAwesome 6.5.2 (via CDN).
- **Backend e Infraestrutura (BaaS):** Firebase SDK v10.8.0.
  - **Firebase Authentication:** Autenticação via Google Sign-In (`signInWithPopup`).
  - **Cloud Firestore:** Banco de dados NoSQL em tempo real com ouvintes ativos (`onSnapshot`).
- **Hospedagem:** GitHub Pages (Servidor de arquivos estáticos).
- **APIs de Navegador:**
  - `Web Speech API` (`SpeechRecognition`) para comandos de voz.
  - `Notifications API` para alertas de vencimento no dispositivo.

---

## 🗄️ 2. Modelagem do Banco de Dados (Cloud Firestore)

A estrutura de dados é organizada hierarquicamente por **Grupos/Casais**:

### Coleção Principal: `grupos_compras/{grupoId}`
Documento do grupo contendo metadados de configuração e controle da casa.
```json
{
  "budget": 1500.00,
  "appVersion": "2.4.0",
  "updatedAt": "Timestamp",
  "members": [
    { "uid": "abc12345", "name": "Nome Usuário", "email": "usuario@gmail.com" }
  ]
}