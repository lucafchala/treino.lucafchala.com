# treino.lucafchala.com

## Aviso de lançamento de álbum (fotos)

O `index.html` carrega `https://fotos.lucafchala.com/destaque.js` (com `async`, antes do `</body>`). O script pergunta a `fotos.lucafchala.com/api/destaque` e **só desenha algo quando o fotos lança um álbum com "Destaque máximo no site"** marcado: uma faixa azul no topo, "TURMA 2026 · COLÉGIO SANTA CRUZ **Entre Nós** · o álbum está no ar · Ver o álbum →". Até lá, nada aparece.

- A faixa vive num shadow root fechado, então o CSS desta página não a afeta e ela não afeta a página. É montada sem `innerHTML` e sem cookie.
- O × esconde a faixa por 3 dias naquele aparelho (`localStorage`).
- Se o fotos estiver fora do ar, nada aparece e a página segue normal.
- O site não tem CSP; se ganhar uma, libere `https://fotos.lucafchala.com` em `script-src` e `connect-src`.
- Para tirar: apague a linha do script.
- O quadro de todos os sites (quais usam este script e quais usam a versão posta pelo servidor) está no `docs/ALBUM.md` do fotos, "Aviso nos outros sites".
