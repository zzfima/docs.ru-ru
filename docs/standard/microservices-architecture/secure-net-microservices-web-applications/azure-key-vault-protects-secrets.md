---
title: Использование Azure Key Vault для защиты секретов в рабочей среде
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Использование Azure Key Vault для защиты секретов в рабочей среде
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 5738b81c90c886aff48451742881807dc09a9ff9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863991"
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="96e2c-103">Использование Azure Key Vault для защиты секретов в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="96e2c-103">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="96e2c-104">Секреты, которые сохраняются в переменных среды или с помощью диспетчера секретов, хранятся на компьютере в локальном и незашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="96e2c-104">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="96e2c-105">Более безопасный способ хранения секретов — хранилище [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), которое предоставляет безопасное централизованное расположение для хранения ключей и секретов.</span><span class="sxs-lookup"><span data-stu-id="96e2c-105">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="96e2c-106">С помощью пакета Microsoft.Extensions.Configuration.AzureKeyVault приложение ASP.NET Core может считывать сведения о конфигурации из Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="96e2c-106">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="96e2c-107">Чтобы приступить к работе с секретами из Azure Key Vault, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="96e2c-107">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="96e2c-108">Во-первых, зарегистрируйте свое приложение как приложение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96e2c-108">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="96e2c-109">(Доступом к хранилищам ключей управляет Azure AD.) Это можно сделать с помощью портала управления Azure.</span><span class="sxs-lookup"><span data-stu-id="96e2c-109">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="96e2c-110">Кроме того, если приложение должно проходить проверку подлинности с помощью сертификата, а не с помощью пароля или секрета клиента, можете использовать командлет PowerShell [New-AzureRmADApplication](https://docs.microsoft.com/powershell/module/azurerm.resources/new-azurermadapplication).</span><span class="sxs-lookup"><span data-stu-id="96e2c-110">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/module/azurerm.resources/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="96e2c-111">Для сертификата, который зарегистрирован в хранилище ключей Azure Key Vault, необходим только ваш открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="96e2c-111">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="96e2c-112">(Приложение будет использовать закрытый ключ.)</span><span class="sxs-lookup"><span data-stu-id="96e2c-112">(Your application will use the private key.)</span></span>

<span data-ttu-id="96e2c-113">Во-вторых, предоставьте зарегистрированному приложению доступ к хранилищу ключей, создав новый субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="96e2c-113">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="96e2c-114">Это можно сделать с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="96e2c-114">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="96e2c-115">В-третьих, включите хранилище ключей как источник конфигурации в своем приложении. Для этого вызовите метод расширения IConfigurationBuilder.AddAzureKeyVault при создании экземпляра IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="96e2c-115">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="96e2c-116">Обратите внимание, что для вызова метода AddAzureKeyVault потребуется идентификатор приложения, которое было зарегистрировано и которому был предоставлен доступ к хранилищу ключей в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="96e2c-116">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="96e2c-117">Сейчас .NET Standard и .NET Core поддерживают получение сведений о конфигурации из Azure Key Vault с помощью идентификатора клиента и секрета клиента.</span><span class="sxs-lookup"><span data-stu-id="96e2c-117">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="96e2c-118">В приложениях .NET можно использовать перегрузку метода IConfigurationBuilder.AddAzureKeyVault, который принимает сертификат вместо секрета клиента.</span><span class="sxs-lookup"><span data-stu-id="96e2c-118">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="96e2c-119">На момент написания этой статьи мы [работаем](https://github.com/aspnet/Configuration/issues/605) над тем, чтобы сделать эту перегрузку доступной в NET Standard и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="96e2c-119">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="96e2c-120">Пока перегрузка метода AddAzureKeyVault, которая принимает сертификат, не стала доступной, приложения ASP.NET Core могут подключаться к Azure Key Vault с помощью проверки подлинности на основе сертификатов путем явного создания объекта KeyVaultClient, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="96e2c-120">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="96e2c-121">В этом примере вызов метода AddAzureKeyVault осуществляется в конце регистрации поставщика конфигурации.</span><span class="sxs-lookup"><span data-stu-id="96e2c-121">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="96e2c-122">Рекомендуется зарегистрировать Azure Key Vault в качестве последнего поставщика конфигурации, чтобы иметь возможность переопределить значения параметров конфигурации от предыдущих поставщиков и чтобы никакие значения параметров конфигурации из других источников не перегружали значения параметров конфигурации из хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="96e2c-122">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="96e2c-123">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="96e2c-123">Additional resources</span></span>

-   <span data-ttu-id="96e2c-124">**Использование Azure Key Vault для защиты секретов приложения**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="96e2c-124">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="96e2c-125">**Безопасное хранение секретов приложений во время разработки**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="96e2c-125">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="96e2c-126">**Настройка защиты данных**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="96e2c-126">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="96e2c-127">**Управление ключами и время их существования**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="96e2c-127">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="96e2c-128">Репозиторий GitHub **Microsoft.Extensions.Configuration.KeyPerFile**.</span><span class="sxs-lookup"><span data-stu-id="96e2c-128">**Microsoft.Extensions.Configuration.KeyPerFile** GitHub repo.</span></span>
    [*https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile*](https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile)

>[!div class="step-by-step"]
<span data-ttu-id="96e2c-129">[Назад](developer-app-secrets-storage.md)
[Вперед](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="96e2c-129">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
