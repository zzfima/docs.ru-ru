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
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="e9499-104">Использование Azure Key Vault для защиты секретов в рабочей среде</span><span class="sxs-lookup"><span data-stu-id="e9499-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="e9499-105">Секреты, которые сохраняются в переменных среды или с помощью диспетчера секретов, хранятся на компьютере в локальном и незашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="e9499-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="e9499-106">Более безопасный способ хранения секретов — хранилище [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), которое предоставляет безопасное централизованное расположение для хранения ключей и секретов.</span><span class="sxs-lookup"><span data-stu-id="e9499-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="e9499-107">С помощью пакета Microsoft.Extensions.Configuration.AzureKeyVault приложение ASP.NET Core может считывать сведения о конфигурации из Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="e9499-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="e9499-108">Чтобы приступить к работе с секретами из Azure Key Vault, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e9499-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="e9499-109">Во-первых, зарегистрируйте свое приложение как приложение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e9499-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="e9499-110">(Доступом к хранилищам ключей управляет Azure AD.) Это можно сделать с помощью портала управления Azure.</span><span class="sxs-lookup"><span data-stu-id="e9499-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="e9499-111">Кроме того, если приложение должно проходить проверку подлинности с помощью сертификата, а не с помощью пароля или секрета клиента, можете использовать командлет PowerShell [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication).</span><span class="sxs-lookup"><span data-stu-id="e9499-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="e9499-112">Для сертификата, который зарегистрирован в хранилище ключей Azure Key Vault, необходим только ваш открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="e9499-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="e9499-113">(Приложение будет использовать закрытый ключ.)</span><span class="sxs-lookup"><span data-stu-id="e9499-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="e9499-114">Во-вторых, предоставьте зарегистрированному приложению доступ к хранилищу ключей, создав новый субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="e9499-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="e9499-115">Это можно сделать с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e9499-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="e9499-116">В-третьих, включите хранилище ключей как источник конфигурации в своем приложении. Для этого вызовите метод расширения IConfigurationBuilder.AddAzureKeyVault при создании экземпляра IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="e9499-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="e9499-117">Обратите внимание, что для вызова метода AddAzureKeyVault потребуется идентификатор приложения, которое было зарегистрировано и которому был предоставлен доступ к хранилищу ключей в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="e9499-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="e9499-118">Сейчас .NET Standard и .NET Core поддерживают получение сведений о конфигурации из Azure Key Vault с помощью идентификатора клиента и секрета клиента.</span><span class="sxs-lookup"><span data-stu-id="e9499-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="e9499-119">В приложениях .NET можно использовать перегрузку метода IConfigurationBuilder.AddAzureKeyVault, который принимает сертификат вместо секрета клиента.</span><span class="sxs-lookup"><span data-stu-id="e9499-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="e9499-120">На момент написания этой статьи мы [работаем](https://github.com/aspnet/Configuration/issues/605) над тем, чтобы сделать эту перегрузку доступной в NET Standard и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e9499-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="e9499-121">Пока перегрузка метода AddAzureKeyVault, которая принимает сертификат, не стала доступной, приложения ASP.NET Core могут подключаться к Azure Key Vault с помощью проверки подлинности на основе сертификатов путем явного создания объекта KeyVaultClient, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e9499-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="e9499-122">В этом примере вызов метода AddAzureKeyVault осуществляется в конце регистрации поставщика конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e9499-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="e9499-123">Рекомендуется зарегистрировать Azure Key Vault в качестве последнего поставщика конфигурации, чтобы иметь возможность переопределить значения параметров конфигурации от предыдущих поставщиков и чтобы никакие значения параметров конфигурации из других источников не перегружали значения параметров конфигурации из хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="e9499-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e9499-124">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e9499-124">Additional resources</span></span>

-   <span data-ttu-id="e9499-125">**Использование Azure Key Vault для защиты секретов приложений**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="e9499-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="e9499-126">**Безопасное хранение секретов приложений во время разработки**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="e9499-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="e9499-127">**Настройка защиты данных**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="e9499-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="e9499-128">**Управление ключами и временем существования**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="e9499-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="e9499-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="e9499-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="e9499-130">Репозиторий GitHub.</span><span class="sxs-lookup"><span data-stu-id="e9499-130">GitHub repo.</span></span>
    [<span data-ttu-id="e9499-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="e9499-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="e9499-132">[Назад] (developer-app-secrets-storage.md) [Далее] (../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="e9499-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
