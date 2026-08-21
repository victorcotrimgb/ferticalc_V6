FertCalc PWA v3 - atualização para GitHub Pages

Arquivos que devem ficar na raiz do repositório:
- index.html
- manifest.webmanifest
- sw.js
- icon.svg
- icon-192.png
- icon-512.png

ATUALIZAÇÃO
1. Faça um backup JSON no FertCalc atual antes de substituir os arquivos.
2. Substitua os arquivos na raiz do repositório pelos arquivos deste pacote.
3. Faça commit/push.
4. Abra o GitHub Pages e recarregue. O service worker tem um cache novo (fertcalc-v3-20260821-1).
5. Se o navegador ainda mostrar a versão antiga, feche o PWA completamente e abra novamente; em último caso, limpe apenas o cache do site, preservando os dados se você já exportou o backup.

MIGRAÇÃO
- O app tenta migrar automaticamente dados de chaves locais com nomes FertCalc/FertiLab, inclusive fertilab_v1.
- IDs de matérias-primas e fórmulas agora são UUIDs independentes do nome/abreviação.
- Fórmulas salvam snapshot das MPs usadas, evitando que uma edição futura da MP altere silenciosamente uma fórmula antiga.

PRINCIPAIS MUDANÇAS
- Aba Fórmulas salvas: abrir/editar, duplicar, excluir e gerar PDF.
- + MP abre popup com MP, kg e prévia de custo/contribuição antes de adicionar.
- Cadastro de nova MP pode ser aberto de dentro desse popup e retorna para a formulação.
- Cada MP mostra kg, % da fórmula, preço/t, custo, % do custo e contribuição de cada nutriente em kg, p.p. e % do nutriente total.
- N Total é preenchido automaticamente quando só as formas de N foram cadastradas.
- Solver automático detalha toda a solução: garantias, MPs, custo, % custo, contribuição por nutriente, matriz de p.p. e origem de cada nutriente.
- Dose mínima operacional evita MPs com quantidades residuais (ex.: 0,01 kg/t).
- PDF inclui garantias calculadas, garantia proposta por truncamento, metas, mínimos regulatórios, formulação, custo e formas de N.
- Compartilhar PDF usa o compartilhamento nativo do celular quando suportado; caso contrário, baixa o PDF.
- Backup JSON completo.

v3.3 — instalação Android/WebAPK
- Manifest, start_url, scope, ícones e service worker agora usam caminhos absolutos do GitHub Pages: /ferticalc_V6/.
- Esta versão é específica para https://victorcotrimgb.github.io/ferticalc_V6/.
- Após publicar, remova o atalho antigo e instale novamente pelo botão "Instalar app".
- Para confirmar WebAPK: FertCalc deve aparecer em Configurações > Aplicativos. Se não aparecer, o navegador criou apenas um atalho.
