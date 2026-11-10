# Integrações — Imagination Hub 7.0

## Pré-requisitos

- Use o backend Node.js e faça login numa conta verificada.
- Credenciais inseridas na área de integrações ficam no cofre AES-256-GCM da instância.
- Não publique `.env`, `.ih-vault-key`, `integration-vault.enc`, `accounts.json` ou `workspaces`.
- “Credencial configurada” não significa “conta conectada”; um teste autenticado confirma a conexão no momento da chamada.

## YouTube / Google

1. Crie um projeto no Google Cloud Console.
2. Ative YouTube Data API v3 e YouTube Analytics API, quando necessária.
3. Configure OAuth consent screen e credenciais OAuth.
4. Cadastre Client ID e Client Secret em Configurações → Integrações e APIs ou no ambiente local.
5. Cadastre o callback exibido pelo Hub.
6. Autorize e teste o canal.

Upload/publicação não são declarados como funcionalidade concluída nesta distribuição.

## TikTok

1. Registre um app no TikTok for Developers.
2. Habilite Login Kit Desktop e os produtos/escopos aprovados.
3. Cadastre Client Key e Client Secret.
4. Use o callback loopback exibido pela interface.
5. Autorize e teste perfil/lista de vídeos.

Limitação: implementação atual é Login Kit Desktop/loopback, não Login Kit Web para hospedagem pública. Publicação não está implementada.

## Instagram / Meta

Configure um app Meta for Developers com Instagram API adequada à conta profissional, cadastre App ID/Secret, configure o callback e autorize uma conta compatível. O acesso real depende de escopos, permissões e revisão da Meta.

## OpenAI, Anthropic Claude e Google Gemini

1. Faça login numa conta verificada do Hub.
2. Em Configurações → Integrações e APIs, guarde a chave de cada provedor.
3. Use o botão de teste/ativação.
4. O AI Assistant usa rotas proxy do backend; o navegador não recebe a chave.
5. Verifique quotas, modelos e disponibilidade na conta oficial.

Salvar uma chave não comprova que uma chamada de modelo funcionou.

## OpenArt

O fluxo atual transfere prompts para um conector MCP oficial conectado à conta do usuário. O Hub prepara e transfere prompts; não hospeda diretamente uma API de geração OpenArt nem confirma renderização sem retorno do serviço.

## O que não está implementado como integração operacional

- Publicação automática/agendamento de posts YouTube, TikTok e Instagram.
- Upload multi-plataforma em uma ação.
- TikTok Login Kit Web.
- API nativa OpenArt no backend.
- Hospedagem multiusuário com credenciais isoladas por pessoa.
