# 🚀 Projeto de Garantia de Qualidade (QA): Validação Funcional & Relatoria de Bugs

[![Status do Projeto](https://img.shields.io/badge/Status-Concluído-success)]()
[![Casos de Teste](https://img.shields.io/badge/Casos%20de%20Teste-4%20Cenários%20Principais-blue)]()
[![Bugs Reportados](https://img.shields.io/badge/Bugs%20Encontrados-4%20Anomalias-critical)]()
[![Metodologia](https://img.shields.io/badge/Foco-Teste%20Funcional%20%7C%20Bug%20Tracking-orange)]()

Documentação e portfólio de engenharia de software focada em **Garantia de Qualidade (QA)**. Este repositório apresenta o planejamento e a execução de testes funcionais, validação de regras de negócio, testes de fronteira e o reporte estruturado de falhas críticas encontradas em ambiente de homologação.

---

## 🎯 Visão Geral do Projeto
O objetivo principal deste ciclo de testes foi auditar fluxos críticos de uma aplicação web de delivery/comércio, cobrindo desde a segurança de rotas deslogadas, aplicação de regras promocionais de cupons (`LUMEFOOD10`), testes de estresse de quantidade em itens de carrinho, até o rastreio rigoroso de inconsistências de interface e regras de cadastro.

---

## 📑 Estrutura do Repositório
* `CASOS DE TESTE MISSÃO QA - AULA 02.pdf` — Documento detalhado contendo os cenários de teste, passos executados, resultados esperados e comportamentos obtidos.
* `Bug Report - Missão QA - Bug Report.csv` — Relatório técnico estruturado com as anomalias detectadas em campo, severidade e evidências em vídeo.

---

## 🧪 Resumo dos Casos de Teste Executados

| ID / Cenário | Objetivo do Teste | Passos Principais | Resultado Obtido | Status |
| :--- | :--- | :--- | :--- | :---: |
| **Cenário 1** <br>Acesso ao Carrinho | Validar a segurança de rotas sem autenticação prévia | 1. Deslogar da conta<br>2. Acessar `/carrinho` via URL direta | Redirecionamento correto para o login com bloqueio de sessão não autorizada. | ✅ **Passou** |
| **Cenário 2** <br>Cupom Promocional | Validar aplicação de desconto e prevenção de uso duplo | 1. Inserir cupom `LUMEFOOD10`<br>2. Tentar aplicar o mesmo cupom 2x | 10% deduzido com precisão e bloqueio efetivo de duplicação pelo sistema. | ✅ **Passou** |
| **Cenário 3** <br>Quantidades Extremas | Testar limites de quantidade (máximo e valor zero) | 1. Inserir valor `0`<br>2. Inserir maior quantidade possível de itens | O sistema recalculou dinamicamente o total e processou os limites corretamente. | ✅ **Passou** |
| **Cenário 4** <br>Custo de Frete | Verificar integridade do valor da taxa de entrega | 1. Selecionar restaurante<br>2. Avançar para checkout e atualizar página | O valor do frete somou-se corretamente ao total e persistiu após refresh. | ✅ **Passou** |

---

## 🐛 Relatório de Bugs & Anomalias (Bug Tracking)

Durante a exploração e execução dos testes, o olhar analítico permitiu identificar falhas de usabilidade, validação de dados e divergências contratuais. Abaixo estão os defeitos reportados:

| ID | Título do Bug | Severidade | Descrição / Comportamento Observado | Evidência |
| :---: | :--- | :---: | :--- | :---: |
| **BUG-01** | Divergência na taxa de entrega | **Alta** | O valor da taxa de entrega exibido no checkout diverge do valor informado no card inicial do restaurante. | [Ver Evidência](https://www.loom.com/share/f4430dc6e27e402892df21d2e07847b6) |
| **BUG-02** | Menu de categorias inativo | **Média** | Ao clicar nas categorias na tela inicial, nenhuma ação ocorre e o usuário fica travado na mesma tela. | [Ver Evidência](https://www.loom.com/share/666c741d13e24154ade23c4b29c50b96) |
| **BUG-03** | Validação frágil em "Nome Completo" | **Média** | O campo de cadastro permite a criação de conta informando apenas um único nome, sem exigir sobrenome. | [Ver Evidência](https://www.loom.com/share/6a3d5f3f803e4f94af6605690633cadb) |
| **BUG-04** | Finalização de pedido sem número de endereço | **Média** | O sistema permite concluir o checkout no campo de "Endereço completo" omitindo o número do local. | [Ver Evidência](https://www.loom.com/share/0dd1486305d2426da49648da47a5ac4a) |

---

## 💡 Competências Aplicadas
* **Design de Casos de Teste:** Aplicação de técnicas de teste funcional, análise de valores limite e verificação de rotas protegidas.
* **Inspeção Crítica & Relatoria de Defeitos:** Classificação precisa de severidade de bugs (Alta/Média), isolamento de falhas e estruturação de passos claros para reprodução pela equipe de desenvolvimento.
* **Documentação Orientada a Negócio:** Capacidade de gerar relatórios auditáveis que facilitam a tomada de decisão e garantem a entrega de software com maior confiabilidade.

---
*Repositório mantido com foco em boas práticas de engenharia de qualidade de software.*
