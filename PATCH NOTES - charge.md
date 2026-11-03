# PATCH NOTES — Carregamento elétrico (hub.frisk.pt/charge)

## 0.1 — 2026-10-27 (proposta inicial)
- Mapa de todos os postos de carregamento de Portugal (continente, Madeira e Açores) a partir do OpenStreetMap, com cor por potência máxima (<22, 22–49, 50–149, ≥150 kW, desconhecida).
- Base de dados no Supabase (`ev_postos`, leitura pública, escrita admin) + botão admin "Atualizar do OpenStreetMap" (remove postos que já não existem). Se a base de dados estiver vazia, a página vai buscar direto ao OpenStreetMap; cópia em cache no browser.
- Filtros (coluna esquerda): potência mínima, incluir sem potência conhecida, tomadas (Tipo 2, CCS, CHAdeMO, Schuko, Tesla), operadores, só acesso público, só gratuitos, mostrar potência no mapa.
- "O meu carro": tomada rápida, autonomia, bateria, carga à partida, mínimo à chegada, carregar até, potência máx. DC.
- Abas: 📍 Perto (10 mais próximos + 5 mais potentes no raio), 🛣️ Percurso (paragens sugeridas com % à chegada e tempo de carga estimado + lista de postos ao longo da rota por km), 📊 Estatísticas (totais, por potência, por tomada, principais operadores).
- Popup: operador/rede, potência, tomadas, lugares, horário, pago, links Google Maps (com "Incluir na rota" quando há percurso), Waze e OpenStreetMap.
