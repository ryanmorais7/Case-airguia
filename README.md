# Case-airguia
# AirGuia, Case de QA

SaaS próprio, em produção real (airguia.com.br), criado para resolver uma dor que vivi como anfitrião de Airbnb: hóspedes cheios de dúvidas sobre Wi-Fi, acesso, regras da casa e o que fazer na região.

**Autor:** Ryan Morais
**Ambiente:** produção (airguia.com.br)
**Data:** setembro de 2026

> Este projeto é de minha autoria, sem restrição de propriedade de terceiros. O código-fonte da aplicação está disponível no repositório principal do produto.

## 📊 Resumo em números

| Camada | Quantidade | Ferramenta |
|---|---|---|
| Testes manuais | 19 casos | Planilha estruturada |
| Testes E2E automatizados | 40+ testes | Cypress |
| Bugs encontrados e documentados | 3 | Relatório formal |

## 🎯 Escopo

**Automatizado (Cypress):** landing page, autenticação, painel do anfitrião completo (17 seções, formulários, CRUD).

**Manual (essa rodada):** landing page e autenticação (validação complementar de usabilidade), e 5 seções priorizadas do painel por risco e complexidade: **Wi-Fi, Acesso, Reservas, Regras e Limpeza**.

## 🔺 Por que testar manualmente o que já tem automação

Com mais de 40 testes Cypress já cobrindo o sistema, o teste manual dessa rodada não repetiu o que a automação já garante. Focou no que só julgamento humano capta bem: comportamento em casos de borda, consistência de dados entre campos dinâmicos, e cenários de uso real que exigem senso crítico, não roteiro fixo.

## 🐛 Bugs encontrados

3 bugs documentados, todos em aberto:

- **BUG-001** (Média): Wi-Fi permite salvar com o campo de senha vazio, sem nenhum aviso ao usuário.
- **BUG-002** (Alta): trocar o tipo de acesso (fechadura eletrônica, chave física, porteiro) não limpa os dados do tipo anterior, deixando informação residual.
- **BUG-003** (Alta): o sistema permite criar uma reserva com data de checkout já no passado, sem alertar, a reserva nasce expirada.

Detalhes completos, com passos de reprodução e recomendação, no relatório de bugs (anexo).

## 🔍 Destaque técnico

> [!IMPORTANT]
> O BUG-003 tem impacto direto no propósito central do produto: se uma reserva pode nascer expirada sem aviso, o hóspede pode nunca chegar a ver o guia, justamente o problema que o AirGuia existe para resolver. Um bug de validação de data, nesse contexto, é também um bug de proposta de valor.

## 📁 Arquivos deste case

- `AirGuia_Casos_de_Teste.xlsx`, planilha completa com os 19 casos manuais
- `AirGuia_Relatorio_de_Bugs.pdf`, relatório formal com os 3 bugs
- Testes Cypress (40+), no repositório principal do produto

## 🛠️ Stack utilizada

HTML, CSS, JavaScript, TypeScript, Supabase (banco de dados e autenticação), Cypress (E2E), Excel e Word/PDF (documentação de testes e bugs).
