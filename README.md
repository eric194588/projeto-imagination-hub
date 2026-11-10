# Imagination Hub

Projeto escolar de plataforma criativa audiovisual, com editor multipista, biblioteca de mídia, ferramentas de áudio, assistência de IA, pesquisa de tendências, referências e módulos de planejamento social.

## Versão de referência

A versão consolidada mais recente disponível no histórico de trabalho é **1.0.4**, baseada na 1.0.3 Hotfix. Ela adiciona testes de regressão para isolamento do armazenamento local entre contas e migração de dados legados.

> **Estado de implantação:** aplicação local para Node.js. Não publicar como SaaS público multiusuário. Sessões, cofre de integrações, armazenamento de mídia e outras partes ainda têm limitações documentadas.

## Como executar

1. Baixe e extraia o pacote de distribuição completo.
2. Entre na pasta `imagination-hub-server`.
3. Instale as dependências com `npm install`.
4. Copie `.env.example` para `.env` e configure apenas os serviços que pretende usar.
5. Execute `npm start`.
6. Abra `http://127.0.0.1:8787`.

Requisitos: Node.js 18 ou superior e navegador moderno. Consulte `INICIAR.txt` no pacote para instruções detalhadas.

## Documentação

- [Auditoria técnica 1.0.3](docs/AUDITORIA_MASTER_1.0.3.md)
- [Hotfix 1.0.4](docs/HOTFIX_1.0.4.md)
- [Validação 1.0.4](docs/VALIDACAO_1.0.4.txt)
- [Arquitetura 7.0](docs/ARQUITETURA_7.0.md)
- [Integrações 7.0](docs/INTEGRACOES_7.0.md)
- [Histórico de versões 7.0](docs/CHANGELOG_7.0.md)
- [Apresentação escolar 7.0](docs/APRESENTACAO_ESCOLAR_7.0.md)

## Limitações conhecidas

- Exportação MP4/H.264 não implementada/validada; WebM depende dos codecs disponíveis no navegador.
- Arquivos binários de mídia permanecem no IndexedDB local; o workspace sincroniza snapshots JSON.
- Publicação automática em redes sociais não implementada.
- OpenArt depende de fluxo/conector externo; não é uma API de geração hospedada pelo backend.
- Automações agendadas persistentes ainda não estão implementadas.
- Integrações externas dependem de credenciais, escopos, revisão e testes com contas reais.

## Segurança

Nunca envie para o Git:
- `.env` ou qualquer arquivo com chaves;
- `.ih-vault-key`, `integration-vault.enc`, `accounts.json`;
- diretórios `data/`, `workspaces/`, `node_modules/`;
- tokens OAuth, senhas, cookies ou arquivos de contas reais.

Use `.env.example` apenas como modelo, sem valores secretos.

## Código-fonte completo

O pacote de distribuição 1.0.4 contém os arquivos executáveis e testes. Esta etapa inicial registra a documentação do projeto no GitHub; o diretório de código completo ainda precisa ser enviado como arquivos individuais ou por Git no computador.
