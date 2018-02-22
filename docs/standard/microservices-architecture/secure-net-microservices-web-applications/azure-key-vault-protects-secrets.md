---
title: "Использование Azure Key Vault для защиты секретов в рабочей среде"
description: "Архитектура микрослужб .NET для контейнерных приложений .NET | Использование Azure Key Vault для защиты секретов в рабочей среде"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb289c7361362c225eac8b9898bac276c4b623b4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>Использование Azure Key Vault для защиты секретов в рабочей среде

Секреты, которые сохраняются в переменных среды или с помощью диспетчера секретов, хранятся на компьютере в локальном и незашифрованном виде. Более безопасный способ хранения секретов — хранилище [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), которое предоставляет безопасное централизованное расположение для хранения ключей и секретов.

С помощью пакета Microsoft.Extensions.Configuration.AzureKeyVault приложение ASP.NET Core может считывать сведения о конфигурации из Azure Key Vault. Чтобы приступить к работе с секретами из Azure Key Vault, выполните следующие действия:

Во-первых, зарегистрируйте свое приложение как приложение Azure AD. (Доступом к хранилищам ключей управляет Azure AD.) Это можно сделать с помощью портала управления Azure.

Кроме того, если приложение должно проходить проверку подлинности с помощью сертификата, а не с помощью пароля или секрета клиента, можете использовать командлет PowerShell [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication). Для сертификата, который зарегистрирован в хранилище ключей Azure Key Vault, необходим только ваш открытый ключ. (Приложение будет использовать закрытый ключ.)

Во-вторых, предоставьте зарегистрированному приложению доступ к хранилищу ключей, создав новый субъект-службу. Это можно сделать с помощью следующих команд PowerShell:

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

В-третьих, включите хранилище ключей как источник конфигурации в своем приложении. Для этого вызовите метод расширения IConfigurationBuilder.AddAzureKeyVault при создании экземпляра IConfigurationRoot. Обратите внимание, что для вызова метода AddAzureKeyVault потребуется идентификатор приложения, которое было зарегистрировано и которому был предоставлен доступ к хранилищу ключей в предыдущих шагах.

  Сейчас .NET Standard и .NET Core поддерживают получение сведений о конфигурации из Azure Key Vault с помощью идентификатора клиента и секрета клиента. В приложениях .NET можно использовать перегрузку метода IConfigurationBuilder.AddAzureKeyVault, который принимает сертификат вместо секрета клиента. На момент написания этой статьи мы [работаем](https://github.com/aspnet/Configuration/issues/605) над тем, чтобы сделать эту перегрузку доступной в NET Standard и .NET Core. Пока перегрузка метода AddAzureKeyVault, которая принимает сертификат, не стала доступной, приложения ASP.NET Core могут подключаться к Azure Key Vault с помощью проверки подлинности на основе сертификатов путем явного создания объекта KeyVaultClient, как показано в следующем примере:

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

В этом примере вызов метода AddAzureKeyVault осуществляется в конце регистрации поставщика конфигурации. Рекомендуется зарегистрировать Azure Key Vault в качестве последнего поставщика конфигурации, чтобы иметь возможность переопределить значения параметров конфигурации от предыдущих поставщиков и чтобы никакие значения параметров конфигурации из других источников не перегружали значения параметров конфигурации из хранилища ключей.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Использование Azure Key Vault для защиты секретов приложений**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **Безопасное хранение секретов приложений во время разработки**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **Настройка защиты данных**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **Управление ключами и временем существования**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets.** Репозиторий GitHub.
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[Назад] (developer-app-secrets-storage.md) [Далее] (../key-takeaways.md)
