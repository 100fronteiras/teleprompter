# Teleprompter

App web (abre no Safari do iPhone e vai para a tela de início). Grava com a câmera frontal e mostra o roteiro no topo da tela, colado na lente.

## Como usar

1. **Roteiro** → Colar, ou Abrir arquivo (o `.md` da pasta `roteiros/`). Do arquivo do projeto, o app pega só o bloco "Para colar no teleprompter".
2. Linha em branco separa blocos. Linha com `•` aparece em amarelo: é tópico para falar solto.
3. **Botão vermelho:** contagem 3-2-1, grava e começa a rolar. Toque no texto pausa ou retoma; arrastar com o dedo volta ou avança.
4. **Refazer bloco:** volta ao começo do bloco atual, pausa a rolagem e marca o tempo. A gravação continua.
5. **1,0×:** troca a velocidade. **Ajustes:** tamanho da letra, largura da coluna, fundo do texto.
6. Ao parar: **Salvar vídeo** (vai para Fotos pelo menu de compartilhar) e **Salvar marcações** (`.json` com o segundo em que cada bloco começou e onde houve refazer). Mandar os dois por AirDrop para a edição.

## Limites conhecidos (verificado 2026-11-02)

- Precisa de HTTPS para usar a câmera; por isso o app tem que estar hospedado.
- Testado no navegador do Mac: roteiro, blocos, rolagem e refazer. **Câmera e gravação ainda não foram testadas no iPhone.**
- Há relato de bug do Safari no iOS 26.6 em que o vídeo da câmera frontal sai deitado (WebKit 323550). O app avisa se acontecer.
- Qualidade: a que o Safari entregar (o app pede 1080p, 30 fps, 12 Mbps). O app nativo continua como plano C.

## Teste de aceite no iPhone

- [ ] O vídeo sai em pé, em 1080p ou mais.
- [ ] Grava 3 min sem travar.
- [ ] Assistindo, a fala não parece leitura.

## Publicação

- Endereço: **https://100fronteiras.github.io/teleprompter/** (GitHub Pages, repositório público `100fronteiras/teleprompter`, publicado em 2026-11-02 com autorização do Denys).
- Esta pasta é o próprio repositório. Mudou o app? Trocar `VERSAO` em `sw.js`, depois `git commit` e `git push`. O site atualiza em cerca de 1 minuto.
- Só o app fica público. Os roteiros colados ficam guardados no celular, não sobem.
