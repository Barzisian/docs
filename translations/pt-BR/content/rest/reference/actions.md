---
title: Ações
intro: 'Com a API de ações, você pode gerenciar e controlar {% data variables.product.prodname_actions %} para uma organização ou repositório.'
redirect_from:
  - /v3/actions
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - API
miniTocMaxHeadingLevel: 3
---


A API de {% data variables.product.prodname_actions %} permite que você gerencie {% data variables.product.prodname_actions %} usando a API REST. {% data reusables.actions.actions-authentication %} {% data variables.product.prodname_github_apps %} exige permissões mencionadas em cada ponto de extremidade. Para obter mais informações, consulte "[Documentação do {% data variables.product.prodname_actions %}](/actions)".

{% for operation in currentRestOperations %}
  {% unless operation.subcategory %}{% include rest_operation %}{% endunless %}
{% endfor %}

## Artefatos

A API de Artefatos permite que você faça o download, exclua e recupere informações sobre artefatos de fluxo de trabalho. {% data reusables.actions.about-artifacts %} Para obter mais informações, consulte "[Dados recorrentes do fluxo de trabalho que usam artefatos](/actions/automating-your-workflow-with-github-actions/persisting-workflow-data-using-artifacts)".

{% data reusables.actions.actions-authentication %} {% data reusables.actions.actions-app-actions-permissions-api %}

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'artifacts' %}{% include rest_operation %}{% endif %}
{% endfor %}

{% ifversion fpt or ghes > 2.22 or ghae or ghec %}
## Permissões

A API de Permissões permite que você defina permissões para quais empresas, organizações e repositórios podem executar {% data variables.product.prodname_actions %}, e quais ações podem ser executadas.{% ifversion fpt or ghec or ghes %} Para obter mais informações, consulte "[Limites de uso, cobrança e administração](/actions/reference/usage-limits-billing-and-administration#disabling-or-limiting-github-actions-for-your-repository-or-organization)".{% endif %}

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'permissions' %}{% include rest_operation %}{% endif %}
{% endfor %}
{% endif %}

## Segredos

A API Segredos permite criar, atualizar, excluir e recuperar informações sobre segredos criptografados. {% data reusables.actions.about-secrets %} Para obter mais informações, consulte "[Criando e usando segredos encriptados](/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets)".

{% data reusables.actions.actions-authentication %} {% data variables.product.prodname_github_apps %} deve ter a permissão `segredos` para usar esta API. Os usuários autenticados devem ter acesso de colaborador em um repositório para criar, atualizar ou ler segredos.

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'secrets' %}{% include rest_operation %}{% endif %}
{% endfor %}

## Executores auto-hospedados

{% data reusables.actions.ae-self-hosted-runners-notice %}

A API de executores auto-hospedados permite que você registre, visualize e exclua executores auto-hospedados. {% data reusables.actions.about-self-hosted-runners %} Para obter mais informações, consulte "[Hospedando seus próprios executores](/actions/hosting-your-own-runners)".

{% data reusables.actions.actions-authentication %} {% data variables.product.prodname_github_apps %} deve ter a permissão de administração `` para repositórios ou a permissão `organization_self_hosted_runners` para as organizações. Os usuários autenticados devem ter acesso de administrador a repositórios ou organizações ou ao escopo `manage_runners:corporativo` para que as empresas usem esta API.

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'self-hosted-runners' %}{% include rest_operation %}{% endif %}
{% endfor %}

## Grupos de runner auto-hospedados

{% data reusables.actions.ae-self-hosted-runners-notice %}

A API dos Grupos de Runners auto-hospedados permite que você gerencie grupos de runners auto-hospedados. Para obter mais informações, consulte "[Gerenciando acesso a runners auto-hospedados usando grupos](/actions/hosting-your-own-runners/managing-access-to-self-hosted-runners-using-groups)".

{% data reusables.actions.actions-authentication %} {% data variables.product.prodname_github_apps %} deve ter a permissão de administração `` para repositórios ou a permissão `organization_self_hosted_runners` para as organizações. Os usuários autenticados devem ter acesso de administrador a repositórios ou organizações ou ao escopo `manage_runners:corporativo` para que as empresas usem esta API.

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'self-hosted-runner-groups' %}{% include rest_operation %}{% endif %}
{% endfor %}

## Fluxos de trabalho

A API de fluxos de trabalho permite que você veja fluxos de trabalho para um repositório. {% data reusables.actions.about-workflows %} Para obter mais informações, consulte "[Automatizando seu fluxo de trabalho com o GitHub Actions](/actions/automating-your-workflow-with-github-actions)".

{% data reusables.actions.actions-authentication %} {% data reusables.actions.actions-app-actions-permissions-api %}

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'workflows' %}{% include rest_operation %}{% endif %}
{% endfor %}

## Trabalhos de fluxo de trabalho

A API de Trabalhos de Fluxo de Trabalho permite que você visualize logs e trabalhos de fluxo de trabalho. {% data reusables.actions.about-workflow-jobs %} Para obter mais informações, consulte "[Sintaxe de fluxo de trabalho para GitHub Actions](/actions/automating-your-workflow-with-github-actions/workflow-syntax-for-github-actions)".

{% data reusables.actions.actions-authentication %} {% data reusables.actions.actions-app-actions-permissions-api %}

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'workflow-jobs' %}{% include rest_operation %}{% endif %}
{% endfor %}

## Execução de fluxo de trabalho

A API de execução de fluxo de trabalho permite que você visualize, execute novamente, cancele e visualize os logs para executar o fluxo de trabalho. {% data reusables.actions.about-workflow-runs %} Para obter mais informações, consulte "[Gerenciando uma execução de fluxo de trabalho](/actions/automating-your-workflow-with-github-actions/managing-a-workflow-run)".

{% data reusables.actions.actions-authentication %} {% data reusables.actions.actions-app-actions-permissions-api %}

{% for operation in currentRestOperations %}
  {% if operation.subcategory == 'workflow-runs' %}{% include rest_operation %}{% endif %}
{% endfor %}
