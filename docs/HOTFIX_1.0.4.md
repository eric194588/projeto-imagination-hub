# Imagination Hub 1.0.4 — Hotfix de isolamento local

**Data:** 09/11/2026  
**Base:** Imagination Hub 1.0.3 Hotfix  
**Tipo:** testes de regressão adicionais e documentação de validação.

## O que mudou

- Criado `test/account-isolation.test.js`, que executa o bloco real de armazenamento do frontend em ambiente isolado com `localStorage` simulado.
- Testada a alternância entre duas contas no mesmo armazenamento: uma conta não lê os projetos da outra.
- Testado que mudar o nome de exibição não altera o namespace associado ao e-mail normalizado.
- Testada a migração de dados legados: a origem é preservada como backup e uma segunda conta não pode reivindicar os mesmos dados.
- Atualizados metadados da versão para 1.0.4 e histórico de alterações.

## O que não mudou

O motor audiovisual, timeline, efeitos, transições, áudio, módulos de IA e integrações foram preservados. Este patch não implementa `accountId` imutável, banco transacional, sessão persistente, KMS, armazenamento de mídia em nuvem, exportação MP4/H.264, publicação social nem scheduler persistente.

## Resultado

A suíte automatizada reportada para esta distribuição contém 19 testes. A validação E2E visual em navegador e a autenticação com serviços externos continuam pendentes; portanto, esta versão permanece indicada para execução local e testes controlados, não para lançamento SaaS público.
