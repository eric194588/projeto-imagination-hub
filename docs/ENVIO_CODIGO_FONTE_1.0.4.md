# Distribuição 1.0.4 — envio do código-fonte

O pacote completo 1.0.4 foi preparado como ZIP na sessão de trabalho. Esta documentação não substitui os arquivos executáveis: o código deve ser extraído para a raiz do repositório antes de considerar a migração concluída.

## Procedimento recomendado no Windows

1. Baixe o arquivo `imagination_hub_1.0.4_hotfix.zip` disponibilizado na conversa.
2. Extraia o conteúdo.
3. Abra a pasta extraída e entre em `imagination-hub-server`.
4. Copie **o conteúdo** dessa pasta para uma pasta local do repositório clonado `projeto-imagination-hub`, mantendo as pastas `test/` e todos os arquivos de documentação.
5. Não copie arquivos locais de segredo ou dados pessoais: `.env`, `.ih-vault-key`, `integration-vault.enc`, `accounts.json`, `data/`, `workspaces/`, `node_modules/`.
6. Abra o terminal na pasta local do repositório e execute:

```powershell
git status
git add .
git status
git commit -m "feat: add Imagination Hub 1.0.4 source"
git push origin main
```

7. Abra o GitHub e confirme que `index.html`, `server.js`, `editor-engine.js`, `app-legacy.js`, `workspace-service.js`, `secret-vault.js`, `test/` e os demais arquivos aparecem na raiz.

## Antes de enviar

- Confirme que o `.gitignore` está presente.
- Verifique `git status` e não envie segredos, tokens ou dados reais de contas.
- Não publique o aplicativo como SaaS multiusuário; consulte as limitações na auditoria.
- O repositório deve conter código-fonte, testes e documentação. Não basta enviar somente o ZIP.

## Situação

A documentação principal e o `.gitignore` já foram registrados no repositório. O código-fonte executável completo ainda precisa ser enviado pelo computador com o procedimento acima; a integração atual não transfere o arquivo ZIP binário nem executa um push Git local.
