---
title: "С помощью хранилища ключей Azure для защиты секретной информации во время производства"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | С помощью хранилища ключей Azure для защиты секретной информации во время производства"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7f922997e8d0c63e206cd68f4efda14985c86b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>С помощью хранилища ключей Azure для защиты секретной информации во время производства

Секретные данные хранятся в переменных среды или средством секрет Manager по-прежнему хранятся локально и на компьютере в незашифрованном виде. — Это более безопасный вариант для хранения секретов [хранилище ключей Azure](https://azure.microsoft.com/services/key-vault/), который предоставляет безопасное централизованного хранения для хранения, ключи и секретные коды.

Пакет Microsoft.Extensions.Configuration.AzureKeyVault позволяет приложению ASP.NET Core для считывания данных конфигурации из хранилища ключей Azure. Чтобы начать использовать секретные данные из хранилища ключей Azure, выполните следующие действия.

Во-первых необходимо зарегистрируйте приложение как приложение Azure AD. (Доступ к ключа хранилища осуществляется с Azure AD). Это можно сделать с помощью портала управления Azure.

Кроме того, если требуется, чтобы приложение для проверки подлинности с помощью сертификата вместо секрета пароль или клиента, можно использовать [New AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) командлета PowerShell. Сертификат, который зарегистрирован в хранилище ключей Azure должен только открытый ключ. (Приложение будет использовать закрытый ключ).

Во-вторых предоставьте доступ зарегистрированного приложения хранилища ключей путем создания нового субъекта-службы. Это можно сделать с помощью следующих команд PowerShell:

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

В-третьих включите хранилище ключей источник конфигурации приложения путем вызова метода расширения IConfigurationBuilder.AddAzureKeyVault при создании экземпляра IConfigurationRoot. Обратите внимание, что вызов AddAzureKeyVault потребуется идентификатор приложения, который был зарегистрирован и получает доступ к хранилищу ключей в предыдущих шагах.

  В настоящее время стандартных .NET и .NET Core поддерживает получение сведений конфигурации из хранилища ключей Azure с помощью идентификатора клиента и секрет клиента. Приложения .NET framework можно использовать перегрузку IConfigurationBuilder.AddAzureKeyVault, принимающий сертификата вместо секрет клиента. На момент написания этой статьи, работа, [выполняется](https://github.com/aspnet/Configuration/issues/605) для предоставления этой перегрузки в стандартных .NET и .NET Core. Пока AddAzureKeyVault перегрузку, которая принимает данные о наличии сертификата, ASP.NET Core приложения могут обращаться к хранилище ключей Azure с проверкой подлинности на основе сертификата путем явного создания объекта KeyVaultClient, как показано в следующем примере:

```csharp
// Configure Key Vault client
var kvClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(async
    (authority, resource, scope) =>
    {
        var cert = // Get certificate from local store/file/key vault etc. as needed
        // From the Microsoft.IdentityModel.Clients.ActiveDirectory pacakge
        var authContext = new AuthenticationContext(authority,
            TokenCache.DefaultShared);
        var result = await authContext.AcquireTokenAsync(resource,
            // From the Microsoft.Rest.ClientRuntime.Azure.Authentication pacakge
            new ClientAssertionCertificate("{Application ID}", cert));
        return result.AccessToken;
    }));

    // Get configuration values from Key Vault
    var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        // Other configuration providers go here.
        .AddAzureKeyVault("{KeyValueUri}", kvClient,
        new DefaultKeyVaultSecretManager());
```

В этом примере вызов AddAzureKeyVault поставляется в конце регистрацию поставщика конфигурации. Рекомендуется зарегистрировать хранилище ключей Azure в качестве последнего поставщика конфигурации, чтобы он имел возможность переопределения значений конфигурации из предыдущей поставщиков, а не значения конфигурации из других источников переопределяют параметры из хранилища ключей.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **С помощью хранилища ключей Azure для защиты приложения секреты**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **Безопасного хранения секрета приложения во время разработки**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **Настройка защиты данных**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **Ключ, управления и временем существования**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#-параметров защиты данных — по умолчанию —*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets.** В репозитории GitHub.
    [*https://github.com/ASPNET/Configuration/Tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[Предыдущие] (разработчик app секреты storage.md) [Далее] (.. / takeaways.md ключ)
