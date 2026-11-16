# SIGA Madeira Android — PWA 1.0

Aplicação HTML/CSS/JavaScript com Leaflet e JSZip, baseada no padrão GTFS Schedule.

## Fonte de dados
Feed SIGA publicado no catálogo MobilityData: https://gtfs.tiim.pt/rede-siga/rede-siga-gtfs.zip
Referência: https://github.com/MobilityData/mobility-database-catalogs/issues/1739
Não foi possível verificar a disponibilidade do servidor do feed no ambiente de desenvolvimento. Não são incluídos dados de demonstração inventados.

## Instalar no Android
1. Publicar o conteúdo desta pasta num alojamento HTTPS (GitHub Pages, Cloudflare Pages, etc.).
2. Abrir o endereço no Chrome Android > menu ⋮ > Adicionar ao ecrã principal / Instalar aplicação.
3. Premir «Atualizar GTFS oficial». Se houver bloqueio CORS, descarregar o ZIP oficial no Chrome e escolher «Importar ZIP GTFS».
4. Selecionar data e carreira. O mapa mostra o traçado e paragens, quando presentes no GTFS.

## Testar no PC
Executar `python -m http.server 8000` nesta pasta e abrir http://localhost:8000 (ou usar outro servidor estático). Não precisa de Docker ou privilégios de administrador.

## Limitações
- Dados carregados na memória do navegador; reiniciar a página exige reimportação.
- Não inclui GPS em tempo real, previsões de chegada ou posicionamento de veículos.
- O mapa-base Leaflet depende de internet, a menos que seja integrado um fornecedor de mapas offline.
- O carregamento direto depende de permissões CORS no servidor GTFS.
- O GTFS Schedule pode conter apenas horários futuros de um intervalo limitado.
- A pesquisa de horários respeita calendar.txt e calendar_dates.txt, quando fornecidos.
- Bibliotecas Leaflet e JSZip são carregadas por CDN; a primeira abertura requer internet.
