# Arquitetura do Imagination Hub 7.0

## Visão geral

A 7.0 é uma evolução incremental do app web local. Mantém o motor Canvas/Web Audio e o backend Node.js da 6.1, mas separa o HTML do JavaScript legado, adiciona o serviço de workspace cifrado e inclui novos módulos de interface.

```text
Browser
 ├─ index.html
 ├─ workspace-v7.css
 ├─ app-legacy.js
 ├─ keyframe-math.js
 ├─ editor-engine.js
 ├─ platforms-ui.js
 └─ workspace-v7.js

Node.js server.js
 ├─ autenticação / sessões / verificação de e-mail
 ├─ AI proxy (OpenAI, Anthropic, Gemini)
 ├─ social-integrations.js (OAuth, status e consultas permitidas)
 ├─ workspace-service.js (projetos JSON, referências, rascunhos e automações)
 ├─ secret-vault.js (AES-256-GCM)
 └─ RSS público / cache de tendências
```

## Fluxo de estado

- `window.IHApp` mantém compatibilidade com a interface anterior.
- `window.IHProfessionalEditor` expõe o estado/editor e operações de importação/exportação.
- `window.IHModules` expõe project manager, media library, timeline, preview, effects, transitions, audio e export.
- `window.IHKeyframeMath` é a biblioteca pura de interpolação.
- `window.IHWorkspace7` expõe ações do workspace e navegação da 7.0.

## Editor e composição

Clipes estão associados a IDs de assets locais. A timeline guarda faixa, posição, duração, entrada/saída da fonte, velocidade, efeitos, transição, volume e propriedades. Preview e WebM usam o compositor Canvas. Keyframes ficam em `clip.keyframes[property]`, em segundos relativos ao início do clipe.

Propriedades animáveis: posição X/Y, escala, rotação, opacidade e volume.

## Projeto e armazenamento

- Projeto avançado: `localStorage` como `ihProfessionalProject:<id>`.
- Projeto legado: `localStorage` como `violetProjects`.
- Mídia binária: IndexedDB/browser local.
- Sync: snapshots JSON enviados para o backend.
- Workspace remoto: arquivos JSON cifrados com AES-256-GCM.
- Limite JSON por projeto: 8 MB. A rota do workspace não aceita mídia binária.

## Segurança

- Senhas usam scrypt com salt aleatório.
- Sessões permanecem em memória nesta versão.
- Verificação de e-mail depende de SMTP.
- Cofre usa AES-256-GCM; chave vem de `IH_MASTER_KEY` ou arquivo local.
- Credenciais não devem ser publicadas no repositório.

## Limites de implantação

Esta versão é para uso local/single-user. O cofre de credenciais é global à instância e as sessões são em memória. Não hospedar para múltiplos usuários externos sem redesenhar identidade, escopo de credenciais, DB, CSRF, rate limiting, storage, HTTPS/proxy e auditoria.
