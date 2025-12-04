🚫 Instagram Message Sidebar Remover

Extensão simples para remover completamente a caixa lateral de mensagens do Instagram Web.

📌 Sobre

Esta extensão remove toda a barra lateral de mensagens do Instagram (Direct), incluindo:

A caixa de conversas

A lista de chats

Os pop-ups de preview

Os alertas e notificações

Ela é ideal para quem:

✔️ Usa Instagram apenas para navegar no feed
✔️ Quer tela limpa e sem distrações
✔️ Não quer ver nenhuma mensagem na interface
✔️ Quer algo leve e sem configurações

⚠️ Nada é modificado na conta — apenas escondido no navegador.

🧩 Como instalar no Google Chrome

Baixe os arquivos da extensão (manifest.json + content.js)

Extraia em uma pasta

Abra no Chrome:
chrome://extensions/

Ative o Modo do Desenvolvedor (canto superior direito)

Clique em “Carregar sem compactação”

Selecione a pasta da extensão

Pronto! A sidebar de mensagens será removida automaticamente ao abrir o Instagram.

🌐 Funciona em outros navegadores?

Sim! Qualquer navegador baseado em Chromium suporta a extensão:

Chrome

Brave

Edge

Opera

Vivaldi

Arc

Instala o mesmo jeito via Modo Desenvolvedor.

📁 Arquivos necessários
manifest.json
{
  "manifest_version": 3,
  "name": "Instagram Message Sidebar Remover",
  "version": "1.0",
  "description": "Remove completamente a caixa lateral de mensagens do Instagram.",
  "content_scripts": [
    {
      "matches": ["*://www.instagram.com/*"],
      "js": ["content.js"],
      "run_at": "document_idle"
    }
  ]
}

content.js
function removeSidebar() {
  const sidebar = document.querySelector("[role='dialog'], aside, .x1n2onr6, ._aa2u");

  if (sidebar) {
    sidebar.remove();
  }
}

// roda imediatamente
removeSidebar();

// roda repetidamente caso o instagram recarregue elementos
setInterval(removeSidebar, 1000);

📜 Permissões

Nenhuma.
A extensão não coleta dados e não acessa sua conta.
Ela só oculta elementos da página.
