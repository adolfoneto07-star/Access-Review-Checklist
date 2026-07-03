# Checklist de Revisão de Acessos (Access Review)

> **Modelo genérico** baseado em boas práticas de mercado (NIST SP 800-53, ISO/IEC 27001, COBIT 2019).  
> Nenhum dado real, sistema proprietário ou metodologia de empresa específica é utilizado.

---

## O que é uma Revisão de Acessos?

A **Revisão de Acessos** (Access Review ou Access Recertification) é um processo periódico e formal de validação dos acessos concedidos a usuários, garantindo que cada permissão ainda seja necessária, adequada e aprovada pelo gestor responsável.

É um controle fundamental de **Identity Governance & Administration (IGA)** e está alinhado aos princípios de:

- **Menor Privilégio**: ninguém deve ter mais acesso do que o necessário.
- **Separação de Funções (SoD)**: revisão identifica acúmulos conflitantes.
- **Auditabilidade**: evidências de aprovação e revogação com rastreabilidade completa.

---

## Frequência Recomendada

| Tipo de Acesso | Frequência | Responsável |
|---------------|-----------|------------|
| Contas privilegiadas (Admin, PAM) | **Trimestral** | CISO + Gestor de IAM |
| Acessos de terceiros / fornecedores | **Trimestral** | Gestor de Contrato + IAM |
| Acessos operacionais (usuários gerais) | **Semestral** | Gestores de Área + IAM |
| Revisão completa do catálogo de papéis | **Anual** | IAM + Compliance |
| Reconciliação: provisionado vs. aprovado | **Mensal** | Equipe IAM |

---

## Escopo desta Documentação

Este checklist cobre três escopos de revisão:

1. [Acessos Corporativos Gerais](#1-acessos-corporativos-gerais) — usuários internos em sistemas ERP, AD, M365 e aplicações.
2. [Contas Privilegiadas (PAM)](#2-contas-privilegiadas-pam) — admins, service accounts, acessos elevados.
3. [Acessos de Terceiros / Fornecedores](#3-acessos-de-terceiros--fornecedores) — prestadores, consultorias, acessos externos.

---

## 1. Acessos Corporativos Gerais

### Fase 1 — Planejamento

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| 1.1 | Definir escopo da campanha: sistemas, perfis e universo de usuários | Gestor de IAM | D-15 |
| 1.2 | Nomear gestor revisor para cada área / sistema | Gestor de IAM + RH | D-15 |
| 1.3 | Definir critérios de decisão: Manter / Revogar / Ajustar Perfil | Gestor de IAM | D-15 |
| 1.4 | Estabelecer prazo total da campanha e SLA de resposta dos gestores | Gestor de IAM | D-15 |
| 1.5 | Preparar templates de evidência (planilha de revisão, formulário de aprovação) | Equipe IAM | D-10 |
| 1.6 | Comunicar início da campanha a todos os gestores revisores | Gestor de IAM | D-5 |

### Fase 2 — Extração de Dados

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| 2.1 | Extrair relatório de todos os usuários ativos por sistema / aplicação | Equipe IAM | D+0 |
| 2.2 | Identificar usuários com afastamento ou desligamento e acessos residuais | Equipe IAM | D+0 |
| 2.3 | Identificar contas sem último login há mais de 90 dias | Equipe IAM | D+0 |
| 2.4 | Identificar contas compartilhadas ou genéricas (ex.: `admin`, `suporte`) | Equipe IAM | D+0 |
| 2.5 | Cruzar lista de colaboradores ativos no RH com acessos provisionados | Equipe IAM + RH | D+1 |
| 2.6 | Validar integridade dos dados: totais, duplicatas, campos obrigatórios | Equipe IAM | D+1 |

### Fase 3 — Distribuição para Revisão

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| 3.1 | Distribuir lista de usuários aos gestores revisores por área | Equipe IAM | D+2 |
| 3.2 | Orientar gestores sobre critérios de decisão e prazo de retorno | Equipe IAM | D+2 |
| 3.3 | Monitorar retorno diariamente e registrar progresso | Equipe IAM | D+3 a D+7 |
| 3.4 | Cobrar pendentes a 48h do prazo final | Equipe IAM | D+8 |
| 3.5 | Escalar gestores sem resposta para a liderança / CISO | Gestor de IAM | D+9 |

### Fase 4 — Análise e Decisão

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| 4.1 | Consolidar todas as respostas dos gestores em base única | Equipe IAM | D+10 |
| 4.2 | Validar justificativas de manutenção de acesso (necessidade de negócio) | Gestor de IAM | D+11 |
| 4.3 | Identificar e listar todos os acessos indicados para revogação | Equipe IAM | D+11 |
| 4.4 | Verificar se aprovações geram conflitos de SoD com papéis já atribuídos | Equipe IAM | D+11 |
| 4.5 | Solicitar aprovação adicional para casos de risco elevado | Gestor de IAM + CISO | D+12 |
| 4.6 | Registrar decisão final para cada usuário / acesso (Manter / Revogar / Ajustar) | Equipe IAM | D+12 |

### Fase 5 — Remediação

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| 5.1 | Executar revogações de acesso conforme lista aprovada | Equipe IAM | D+13 a D+15 |
| 5.2 | Executar ajustes de perfil (downgrade de permissões) | Equipe IAM | D+13 a D+15 |
| 5.3 | Registrar cada ação com número de ticket / chamado | Equipe IAM | D+15 |
| 5.4 | Confirmar execução: validar no sistema que o acesso foi removido / alterado | Equipe IAM | D+15 |
| 5.5 | Comunicar aos gestores as revogações realizadas na sua equipe | Equipe IAM | D+15 |

### Fase 6 — Evidência e Documentação

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| 6.1 | Registrar resultado final de cada usuário (Mantido / Revogado / Ajustado) | Equipe IAM | D+16 |
| 6.2 | Arquivar aprovações dos gestores (e-mail, ticket ou workflow) | Equipe IAM | D+16 |
| 6.3 | Gerar relatório executivo com métricas da campanha | Gestor de IAM | D+17 |
| 6.4 | Armazenar evidências por período mínimo definido pela política (recomendado: 2 anos) | Equipe IAM | D+17 |

### Fase 7 — Encerramento

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| 7.1 | Apresentar relatório final para CISO / Diretoria | Gestor de IAM | D+18 |
| 7.2 | Registrar métricas: % mantido, % revogado, SLA médio de resposta | Equipe IAM | D+18 |
| 7.3 | Documentar riscos identificados e ações de melhoria | Gestor de IAM + Compliance | D+18 |
| 7.4 | Agendar a próxima campanha conforme frequência definida | Gestor de IAM | D+18 |

---

## 2. Contas Privilegiadas (PAM)

> 🔴 **Frequência: Trimestral** — controles adicionais obrigatórios.

### Critérios Específicos

- Qualquer conta com acesso administrativo local ou de domínio está no escopo.
- Contas de serviço (service accounts) devem ser incluídas mesmo sem login interativo.
- Revisão exige **aprovação dupla**: Gestor de TI + Analista de Segurança / CISO.
- Contas sem uso há mais de **30 dias** devem ser revogadas imediatamente.

### Checklist PAM

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| P.1 | Inventariar todas as contas privilegiadas (admins locais, admins de domínio, service accounts, contas de banco de dados) | Equipe IAM + TI | D+0 |
| P.2 | Verificar se cada conta privilegiada tem um responsável nominado (owner) | Gestor de TI | D+1 |
| P.3 | Checar contas sem atividade nos últimos 30 dias → revogar imediatamente | Equipe IAM | D+1 |
| P.4 | Validar se senhas de contas privilegiadas foram rotacionadas conforme política | Equipe IAM + TI | D+1 |
| P.5 | Verificar gravação de sessão ativa para contas com acesso Just-in-Time (JIT) | Equipe de Segurança | D+2 |
| P.6 | Validar que acessos temporários JIT expiram conforme configurado | Equipe IAM | D+2 |
| P.7 | Revisar lista de service accounts: verificar finalidade, sistemas utilizados e dono | Gestor de TI | D+3 |
| P.8 | Confirmar que service accounts não possuem login interativo habilitado | Equipe TI | D+3 |
| P.9 | Submeter lista de contas mantidas para aprovação dupla (TI + Segurança) | Gestor de IAM | D+4 |
| P.10 | Executar revogações aprovadas e confirmar no Active Directory / sistema | Equipe IAM | D+5 |
| P.11 | Gerar evidência com lista de contas privilegiadas ativas pós-revisão | Equipe IAM | D+5 |
| P.12 | Reportar resultados ao CISO com métricas e riscos identificados | Gestor de IAM | D+6 |

---

## 3. Acessos de Terceiros / Fornecedores

> 🟡 **Frequência: Trimestral** — nenhum acesso permanente deve existir para terceiros.

### Critérios Específicos

- Todo acesso de terceiro deve ter **data de expiração** definida no momento da concessão.
- A aprovação de manutenção exige confirmação de **contrato ativo** com o fornecedor.
- Acessos sem atividade há mais de **60 dias** devem ser revogados imediatamente.
- Terceiros **não devem** ter acesso a sistemas de produção sem supervisão ou registro de sessão.

### Checklist Terceiros

| # | Passo | Responsável | SLA |
|---|-------|------------|-----|
| T.1 | Inventariar todos os acessos ativos de terceiros / fornecedores | Equipe IAM | D+0 |
| T.2 | Validar que cada acesso de terceiro possui um gestor de contrato responsável | Equipe IAM + Compras | D+0 |
| T.3 | Verificar se o contrato / NDA do fornecedor está ativo e vigente | Gestor de Contrato | D+1 |
| T.4 | Identificar acessos de terceiros sem atividade há mais de 60 dias → revogar imediatamente | Equipe IAM | D+1 |
| T.5 | Identificar acessos sem data de expiração definida → definir prazo ou revogar | Equipe IAM | D+1 |
| T.6 | Confirmar que terceiros acessam apenas os sistemas previstos no escopo do contrato | Gestor de Contrato + IAM | D+2 |
| T.7 | Verificar que acessos de terceiros a ambientes de produção possuem log / gravação de sessão | Equipe de Segurança | D+2 |
| T.8 | Submeter lista de acessos para aprovação dos gestores de contrato | Equipe IAM | D+3 |
| T.9 | Executar revogações de acessos não aprovados ou com contrato expirado | Equipe IAM | D+4 |
| T.10 | Renovar acessos aprovados com nova data de expiração | Equipe IAM | D+4 |
| T.11 | Gerar evidência com lista de acessos de terceiros ativos pós-revisão | Equipe IAM | D+4 |
| T.12 | Comunicar fornecedores com acessos revogados | Gestor de Contrato | D+5 |

---

## Métricas da Campanha

Ao encerrar cada campanha, registrar obrigatoriamente:

| Métrica | Descrição |
|---------|-----------|
| **Total de usuários revisados** | Universo total incluído na campanha |
| **% Mantido** | Proporção de acessos confirmados pelos gestores |
| **% Revogado** | Proporção de acessos removidos |
| **% Ajustado** | Proporção de acessos com mudança de perfil/nível |
| **SLA médio de resposta** | Tempo médio de retorno dos gestores revisores |
| **% de gestores que responderam no prazo** | Indicador de engajamento do processo |
| **Contas sem dono identificado** | Contas órfãs encontradas durante a extração |
| **Conflitos de SoD identificados** | Acúmulos detectados durante a análise |

---

## Principais Riscos de Não Conformidade

| Risco | Impacto | Controle |
|-------|---------|---------|
| Acessos residuais de ex-colaboradores | Alto — acesso indevido a sistemas críticos | Revisão mensal cruzada com folha de pagamento |
| Acúmulo de privilégios (Privilege Creep) | Alto — violação do princípio de menor privilégio | Revisão semestral + SoD check na concessão |
| Contas privilegiadas sem owner | Crítico — sem responsabilidade ou rastreabilidade | Inventário trimestral com owner obrigatório |
| Acessos de terceiros sem expiração | Alto — acesso permanente não autorizado | Bloqueio técnico de concessão sem data de fim |
| Gestores sem resposta na campanha | Médio — acessos não revisados ficam ativos | Escalada automática para liderança após D+8 |

---

## Referências

- NIST SP 800-53 Rev. 5 — AC-2 (Account Management), AC-6 (Least Privilege)
- ISO/IEC 27001:2022 — Annex A, Control 5.18 (Access Rights), 8.2 (Privileged Access Rights)
- COBIT 2019 — DSS05 (Manage Security Services), DSS06 (Manage Business Process Controls)
- IIA GTAG — Identity and Access Management
- CIS Controls v8 — Control 5 (Account Management), Control 6 (Access Control Management)

---

*Autor: Adolfo Neto | IAM & Information Security Analyst*  
*Modelo genérico para fins educacionais e de referência profissional.*
