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

## 0.2 — 2026-10-27
- Base de dados de preços no Supabase: tabelas `gas_postos` e `gas_precos` (um registo por posto + combustível + data de atualização; se o mesmo posto/combustível/data voltar a ser importado, grava o valor novo). Leitura pública, escrita só admin.
- Importar Excel (.xlsx) ou CSV da DGEG (admin, aba Análise → "⬆ Atualizar base de dados").
- Seletor de combustível (todos os combustíveis importados); o mapa e as tabelas usam o preço mais recente de cada posto.
- Nova aba "📈 Análise": evolução do preço médio por marca (comparar até 10 marcas + média nacional), ranking de marcas (preço médio, variação no período, nº postos) e evolução por posto (todos os combustíveis + lista de alterações). Link "📈 Evolução" no popup de cada posto.
- Caixa "Percursos recorrentes" minimizada por defeito.
- Cópia de reserva embutida (Gasolina 95 de 26/10) e cache no browser se a base de dados não responder.

## 0.2a — 2026-10-27
- Coluna à esquerda, comum a todas as abas, com duas caixas:
  - **Geral**: combustível, marcas, mostrar marca no mapa, excluir auto-estradas, aplicar descontos.
  - **Valores de referência**: perfis com nome (veículo, tipo de combustível, consumo, depósito, litros a abastecer, valor do tempo €/h, afastamento máx. da rota, descontos/cartões/promoções por marca em €/L ou %). Gravados na conta frisk.pt (`user_site_data`, chave `perfis`); sem login ficam no browser.
- Escolher um perfil muda o combustível da caixa Geral para o do veículo.
- Descontos aplicados aos preços (mapa, tabelas, recomendações), com o preço original riscado; se vários se aplicarem, conta o maior.
- Custo dos recomendados inclui o valor do tempo do desvio.
- Tabelas "Perto" mostram o custo de abastecer os litros do perfil.
- Telemóvel: as caixas abrem num painel lateral pelo botão ⚙️.
- Afastamento, litros e consumo saíram da aba Percurso (agora no perfil), com um resumo do perfil ativo.
