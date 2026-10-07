# Gabinete em Jogo

Jogo criado com auxílio de IA.

Jogo de plataforma para navegador, com um investigador fictício que coleta documentos sobre casos envolvendo Flávio Bolsonaro. A sátira usa obstáculos fictícios; as fichas apresentam fontes e distinguem acusações de decisões judiciais.

[Jogar a versão atual](https://gabinete-em-jogo.lindemberg-frank.chatgpt.site)

## Estado do projeto

Protótipo jogável com três fases sobre o caso das rachadinhas. Os cenários das fases ainda compartilham o mesmo mapa e os nove itens coletáveis desbloqueiam três fichas de contexto, uma por fase. Não é um levantamento completo das controvérsias envolvendo o senador.

## Jogar localmente

Requer Python 3 apenas para servir os arquivos:

```sh
python -m http.server 8000 --directory dist
```

Abra http://localhost:8000. Use A/D ou setas para mover, espaço para pular e P para pausar. No celular, use os botões na tela. Reúna os três documentos de cada fase e alcance o terminal verde.

## Estrutura

- `dist/index.html`: interface e dossiê.
- `dist/style.css`: layout e controles responsivos.
- `dist/game.js`: movimento, colisões, fases e fichas.
- `dist/archive.webp`: cenário original gerado para o jogo.
- `.github/workflows/pages.yml`: publicação no GitHub Pages.

HTML, CSS e JavaScript sem dependências de execução, login, rastreamento ou servidor de aplicação. O personagem atual usa um emoji e pode variar conforme o sistema operacional.

## GitHub Pages

Após enviar o projeto ao repositório, selecione **Settings → Pages → Build and deployment → Source → GitHub Actions**. O workflow publica `dist` em cada push para `main`, ou manualmente pela aba Actions. A disponibilidade de Pages em repositório privado depende do plano da conta; um repositório público permite a distribuição pública no plano gratuito.

## Fontes e critérios editoriais

Veja [FONTES.md](FONTES.md) para a lista das fontes utilizadas, referências auxiliares, créditos de arte e o alcance de cada documento.

Fontes consultadas em 07/10/2026:

- [MPRJ — denúncia anunciada em 04/11/2020](https://transparencia.mprj.mp.br/web/guest/visualizar?noticiaId=96203).
- [TJRJ — rejeição da denúncia em 16/05/2022](https://www.tjrj.jus.br/home?_com_liferay_portal_search_web_portlet_SearchPortlet_assetEntryId=92111651&_com_liferay_portal_search_web_portlet_SearchPortlet_mvcPath=%2Fview_content.jsp&p_p_id=com_liferay_portal_search_web_portlet_SearchPortlet&p_p_lifecycle=0&p_p_state=maximized).

Cada novo episódio deve registrar a fonte, a data, o que foi alegado, a resposta do envolvido e o desfecho conhecido. Não inferir culpa de investigação, associação ou notícia; não omitir decisões posteriores relevantes. Flávio nega irregularidades. Personagem e obstáculos não representam acontecimentos reais.

## Próximos passos

- Criar mapas distintos e sprites animados originais.
- Testar a experiência visual e os controles em dispositivos reais.
- Expandir os episódios após pesquisa e verificação das fontes.
- Separar os dados do dossiê da lógica do jogo.

## Verificação

```sh
node --check dist/game.js
```

A primeira versão passou por verificações da lógica de aterrissagem, salto, movimento e conclusão de fase. A validação visual em navegadores e aparelhos reais permanece pendente.
