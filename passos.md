# Controlo ETAR – Europastry (app instalável)

## O que contém
- `index.html` – a aplicação (registo de parâmetros, consumos, histórico, gráficos, exportação e envio por email)
- `manifest.webmanifest` – nome, cores e ícones da app
- `sw.js` – permite usar a app sem rede
- `icons/` – ícones para o ecrã principal

## 1. Colocar num endereço https (uma vez)
A app só se pode instalar a partir de um endereço **https**. Escolha uma opção:

**A) Servidor interno / TI (recomendado na empresa)**
Peça à TI para publicar o conteúdo desta pasta num site interno (IIS, Apache, Nginx ou Azure Static Web Apps). Não precisa de base de dados nem de configuração especial.
Nota: o SharePoint não serve para isto, porque não executa páginas HTML.

**B) GitHub Pages (gratuito, mais rápido para testar)**
1. Crie uma conta em github.com e um repositório novo (por exemplo `etar`).
2. Envie para lá todos os ficheiros e pastas deste pacote (botão *Add file > Upload files*).
3. Em *Settings > Pages*, escolha *Deploy from a branch*, ramo `main`, pasta `/ (root)`.
4. Passado um minuto, a app fica em `https://SEU-UTILIZADOR.github.io/etar/`.
Atenção: num repositório público qualquer pessoa com o link vê a app (não contém dados, os registos ficam em cada dispositivo).

**Teste rápido no PC (sem publicar)**
Abra um terminal nesta pasta e execute `python -m http.server 8000`; depois abra `http://localhost:8000` no Chrome.

## 2. Instalar no Android
1. Abra o endereço no **Chrome**.
2. Menu (três pontos) > **Instalar aplicação** (ou *Adicionar ao ecrã principal*).
3. Fica um ícone no ecrã principal e a app abre em ecrã inteiro.

## 3. Email com anexo
No botão **Enviar por email**, a app abre a folha de partilha do Android com o ficheiro CSV já anexado; escolha Outlook ou Gmail. Se o dispositivo não suportar, grava o ficheiro e abre um rascunho de email para anexar manualmente.

## 4. Dados e atualizações
- Os registos ficam guardados **no browser de cada dispositivo**, ligados ao endereço da app. Se mudar de endereço, a app começa vazia: exporte o CSV antes.
- Para publicar uma versão nova, substitua o `index.html` e aumente o número em `CACHE` no `sw.js` (por exemplo `etar-v2`), para os telemóveis atualizarem.
- O ícone foi desenhado a partir do símbolo do trigo; se tiver o ficheiro oficial do logo, substitua os ficheiros da pasta `icons/` mantendo os mesmos nomes e tamanhos.
