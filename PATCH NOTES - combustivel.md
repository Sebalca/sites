# PATCH NOTES — Combustível (hub.frisk.pt/combustivel)

## 0.1 — 2026-10-27
- Mapa dos postos de Gasolina simples 95 (CSV DGEG, preços até 26/10/2026), com localização (GPS) e tabelas dos 5 mais baratos e 5 mais próximos.

## 0.1a
- Pesquisa de morada/coordenadas e escolha de local no mapa (📌).
- Aba "Percurso": rota A→B (OSRM), postos até X km da rota, 5 recomendados por custo (abastecimento + desvio) e 5 mais baratos.

## 0.1b
- Recomendados mostram o tempo e km de desvio real (A → posto → B) face ao percurso original.

## 0.1c
- Filtro por marca (combo com pesquisa, várias marcas).
- Opção "Mostrar marca no mapa" (etiqueta com sigla e cor da marca).

## 0.1d
- Botão "⭐ Percurso recorrente": grava o percurso calculado (com nome) na conta frisk.pt (Supabase, `user_site_data`, site `combustivel`, chave `percursos`).
- Lista de percursos recorrentes com seleção, ver no mapa, renomear e apagar.
- "Recomendar nos selecionados": top 5 global (preço + desvio) em todos os percursos selecionados, indicando o percurso de cada posto.
- Login/criar conta no próprio site (sessão partilhada com o hub).
- Correção: o campo de origem/destino já não volta a recalcular a rota ao perder o foco.
