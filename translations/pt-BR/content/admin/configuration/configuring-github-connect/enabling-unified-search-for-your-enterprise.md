---
title: Enabling unified search for your enterprise
shortTitle: Unified search
intro: 'You can allow users to include repositories on {% data variables.product.prodname_dotcom_the_website %} in their search results when searching from {% data variables.product.product_location %}.'
redirect_from:
  - /enterprise/admin/guides/developer-workflow/enabling-unified-search-between-github-enterprise-and-github-com
  - /enterprise/admin/guides/developer-workflow/enabling-unified-search-between-github-enterprise-server-and-github-com
  - /enterprise/admin/developer-workflow/enabling-unified-search-between-github-enterprise-server-and-githubcom
  - /enterprise/admin/installation/enabling-unified-search-between-github-enterprise-server-and-githubcom
  - /enterprise/admin/configuration/enabling-unified-search-between-github-enterprise-server-and-githubcom
  - /admin/configuration/enabling-unified-search-between-github-enterprise-server-and-githubcom
  - /admin/configuration/managing-connections-between-github-enterprise-server-and-github-enterprise-cloud/enabling-unified-search-between-github-enterprise-server-and-githubcom
  - /admin/configuration/managing-connections-between-your-enterprise-accounts/enabling-unified-search-between-your-enterprise-account-and-githubcom
permissions: 'Enterprise owners who are also owners of the connected {% data variables.product.prodname_ghe_cloud %} organization or enterprise account can enable unified search between {% data variables.product.product_name %} and {% data variables.product.prodname_dotcom_the_website %}.'
versions:
  ghes: '*'
  ghae: '*'
type: how_to
topics:
  - Enterprise
  - GitHub Connect
  - GitHub search
---

## Sobre o {% data variables.product.prodname_unified_search %}

{% data reusables.github-connect.beta %}

When you enable unified search, users can view search results from content on {% data variables.product.prodname_dotcom_the_website %} when searching from {% data variables.product.product_location %}{% ifversion ghae %} on {% data variables.product.prodname_ghe_managed %}{% endif %}.

You can choose to allow search results for public repositories on {% data variables.product.prodname_dotcom_the_website %}, and you can separately choose to allow search results for private repositories on {% data variables.product.prodname_ghe_cloud %}. If you enable unified search for private repositories, users can only search private repositories that they have access to and that are owned by the connected organization or enterprise account. Para obter mais informações, consulte "[Sobre a pesquisa no {% data variables.product.prodname_dotcom %}](/search-github/getting-started-with-searching-on-github/about-searching-on-github/#searching-across-github-enterprise-and-githubcom-simultaneously)".

Users will never be able to search {% data variables.product.product_location %} from {% data variables.product.prodname_dotcom_the_website %}, even if they have access to both environments.

After you enable unified search for {% data variables.product.product_location %}, before individual users can see search results from {% data variables.product.prodname_dotcom_the_website %} on {% data variables.product.product_location %}, each user must also connect their personal account on {% data variables.product.product_name %} with a personal account on {% data variables.product.prodname_dotcom_the_website %}. Para obter mais informações, consulte "[Habilitando a pesquisa de repositório {% data variables.product.prodname_dotcom_the_website %} na sua conta corporativa privada](/search-github/getting-started-with-searching-on-github/enabling-githubcom-repository-search-from-your-private-enterprise-environment)".

A pesquisa via APIs REST e GraphQL não inclui resultados do {% data variables.product.prodname_dotcom_the_website %}. Não há suporte para a pesquisa avançada e a pesquisa de wikis no {% data variables.product.prodname_dotcom_the_website %}.

## Habilitar o {% data variables.product.prodname_unified_search %}

Before you can enable {% data variables.product.prodname_unified_search %}, you must enable {% data variables.product.prodname_github_connect %}. For more information, see "[Managing {% data variables.product.prodname_github_connect %}](/admin/configuration/configuring-github-connect/managing-github-connect)."

{% ifversion ghes %}
{% data reusables.github-connect.access-dotcom-and-enterprise %}
{% data reusables.enterprise_site_admin_settings.access-settings %}
{% data reusables.enterprise_site_admin_settings.business %}
{% ifversion ghes < 3.1 %}{% data reusables.enterprise-accounts.settings-tab %}{% endif %}{% data reusables.enterprise-accounts.github-connect-tab %}{% else %}
1. Efetue o login em {% data variables.product.product_location %} e {% data variables.product.prodname_dotcom_the_website %}.
{% data reusables.enterprise-accounts.access-enterprise %}{% data reusables.enterprise-accounts.github-connect-tab %}{% endif %}
1. Under "Users can search {% data variables.product.prodname_dotcom_the_website %}", use the drop-down menu and click **Enabled**. ![Habilitar a opção de pesquisa no menu suspenso de pesquisa do GitHub.com](/assets/images/enterprise/site-admin-settings/github-dotcom-enable-search.png)
1. Optionally, under "Users can search private repositories on {% data variables.product.prodname_dotcom_the_website %}", use the drop-down menu and click **Enabled**. ![Habilitar a opção de pesquisa em repositórios privados no menu suspenso de pesquisa do GitHub.com](/assets/images/enterprise/site-admin-settings/enable-private-search.png)
