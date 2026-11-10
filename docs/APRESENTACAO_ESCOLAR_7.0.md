# Imagination Hub 7.0 — apresentação do projeto

## O que é

Imagination Hub é uma plataforma criativa web, desenvolvida como projeto escolar, que reúne edição audiovisual local, organização de mídia, assistência de IA, pesquisa de referências, planejamento de conteúdo social e integrações externas.

## Evolução até a 7.0

- 1.0 a 5.2: protótipos, organização de mídia, AI Studio, separação entre geração e edição e ampliação de áudio/efeitos.
- 6.0: motor próprio de edição multipista com Canvas e Web Audio.
- 6.1: backend Node.js, cofre AES-GCM, Central de Plataformas e base de OAuth.
- 7.0: workspace cifrado, autenticação aprimorada, keyframes e módulos de áudio, pesquisa, referências, social e automação.

## Tecnologias

HTML5, CSS, JavaScript, Canvas 2D, Web Audio API, MediaRecorder, IndexedDB, localStorage, Node.js, HTTP nativo, AES-256-GCM, scrypt, OAuth 2.0 e RSS público.

## Recursos

- Importar mídia e organizar timeline multipista.
- Editar clipes, dividir, aparar, duplicar, desfazer/refazer e aplicar transições/filtros.
- Animar posição, escala, rotação, opacidade e volume com keyframes.
- Exportar WebM (quando suportado), PNG, WAV e JSON.
- Guardar snapshots JSON em workspace remoto autenticado/cifrado.
- Guardar referências e rascunhos sociais.
- Consultar feeds públicos.
- Preparar solicitações para IA via API autenticada.

## Limitações e honestidade técnica

A versão 7.0 não implementa MP4/H.264, geração OpenArt hospedada pelo Hub, publicação social automática, cloud media storage ou hospedagem multiusuário pública. Integrações sociais precisam de credenciais e permissões oficiais. Mídias binárias continuam locais, enquanto o sync transfere JSON.

## Objetivo futuro

Separar o legado em módulos menores, migrar para banco transacional e object storage, criar render worker para MP4, adicionar filas persistentes e expandir recursos após validação real.
