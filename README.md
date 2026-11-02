# Teleprompter

App web (abre no Safari do iPhone e vai para a tela de início). Grava com a câmera frontal e mostra o roteiro no topo da tela, colado na lente.

## Como usar

1. **Roteiro** → Colar, ou Abrir arquivo (o `.md` da pasta `roteiros/`). Do arquivo do projeto, o app pega só o bloco "Para colar no teleprompter".
2. Linha em branco separa blocos. Linha com `•` aparece em amarelo: é tópico para falar solto.
3. **Botão vermelho:** contagem 3-2-1, grava e começa a rolar. Toque no texto pausa ou retoma; arrastar com o dedo volta ou avança.
4. **Refazer bloco:** volta ao começo do bloco atual, pausa a rolagem e marca o tempo. A gravação continua.
5. **− e +** (embaixo do texto): velocidade de 0,5× a 2,5×, de 0,1 em 0,1, inclusive gravando. 1,0× = 160 palavras por minuto, seu ritmo medido. Dedo segurando o texto faz a rolagem esperar; ao soltar, ela continua. **Início** volta ao começo. **Ajustes:** tamanho da letra, largura da coluna, fundo do texto.
6. Ao parar: **Salvar vídeo** (vai para Fotos pelo menu de compartilhar) e **Salvar marcações** (`.json` com o segundo em que cada bloco começou e onde houve refazer). Mandar os dois por AirDrop para a edição.

## Limites conhecidos (verificado 2026-11-02)

- Precisa de HTTPS para usar a câmera; por isso o app tem que estar hospedado.
- iPhone, 2026-11-02 (78 s): vídeo em pé, 1920×1080 com rotação, 30 fps, H.264/AAC. O bug de vídeo deitado (WebKit 323550) não aconteceu.
- O MP4 desse teste saiu com a contagem de tempo quebrada: congelava aos 14 s no Fotos, com o áudio seguindo. Os quadros estavam todos lá. Causa provável: gravação fatiada (`start(1000)`); desde 2026-11-02 o app grava sem fatiar. Vídeo que congelar: `bash ../consertar-video.sh <arquivo>` remonta e gera `-CONSERTADO.mp4`.
- Qualidade: a que o Safari entregar (o app pede 1080p, 30 fps, 12 Mbps). O app nativo continua como plano C.

## Teste de aceite no iPhone

- [ ] O vídeo sai em pé, em 1080p ou mais.
- [ ] Grava 3 min sem travar.
- [ ] Assistindo, a fala não parece leitura.

## Publicação

- Endereço: **https://100fronteiras.github.io/teleprompter/** (GitHub Pages, repositório público `100fronteiras/teleprompter`, publicado em 2026-11-02 com autorização do Denys).
- Esta pasta é o próprio repositório. Mudou o app? Trocar `VERSAO` em `sw.js`, depois `git commit` e `git push`. O site atualiza em cerca de 1 minuto.
- Só o app fica público. Os roteiros colados ficam guardados no celular, não sobem.
