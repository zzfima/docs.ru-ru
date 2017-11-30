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
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="109c3-104">С помощью хранилища ключей Azure для защиты секретной информации во время производства</span><span class="sxs-lookup"><span data-stu-id="109c3-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="109c3-105">Секретные данные хранятся в переменных среды или средством секрет Manager по-прежнему хранятся локально и на компьютере в незашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="109c3-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="109c3-106">— Это более безопасный вариант для хранения секретов [хранилище ключей Azure](https://azure.microsoft.com/services/key-vault/), который предоставляет безопасное централизованного хранения для хранения, ключи и секретные коды.</span><span class="sxs-lookup"><span data-stu-id="109c3-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="109c3-107">Пакет Microsoft.Extensions.Configuration.AzureKeyVault позволяет приложению ASP.NET Core для считывания данных конфигурации из хранилища ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="109c3-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="109c3-108">Чтобы начать использовать секретные данные из хранилища ключей Azure, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="109c3-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="109c3-109">Во-первых необходимо зарегистрируйте приложение как приложение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="109c3-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="109c3-110">(Доступ к ключа хранилища осуществляется с Azure AD). Это можно сделать с помощью портала управления Azure.</span><span class="sxs-lookup"><span data-stu-id="109c3-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="109c3-111">Кроме того, если требуется, чтобы приложение для проверки подлинности с помощью сертификата вместо секрета пароль или клиента, можно использовать [New AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) командлета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="109c3-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="109c3-112">Сертификат, который зарегистрирован в хранилище ключей Azure должен только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="109c3-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="109c3-113">(Приложение будет использовать закрытый ключ).</span><span class="sxs-lookup"><span data-stu-id="109c3-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="109c3-114">Во-вторых предоставьте доступ зарегистрированного приложения хранилища ключей путем создания нового субъекта-службы.</span><span class="sxs-lookup"><span data-stu-id="109c3-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="109c3-115">Это можно сделать с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="109c3-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="109c3-116">В-третьих включите хранилище ключей источник конфигурации приложения путем вызова метода расширения IConfigurationBuilder.AddAzureKeyVault при создании экземпляра IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="109c3-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="109c3-117">Обратите внимание, что вызов AddAzureKeyVault потребуется идентификатор приложения, который был зарегистрирован и получает доступ к хранилищу ключей в предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="109c3-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="109c3-118">В настоящее время стандартных .NET и .NET Core поддерживает получение сведений конфигурации из хранилища ключей Azure с помощью идентификатора клиента и секрет клиента.</span><span class="sxs-lookup"><span data-stu-id="109c3-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="109c3-119">Приложения .NET framework можно использовать перегрузку IConfigurationBuilder.AddAzureKeyVault, принимающий сертификата вместо секрет клиента.</span><span class="sxs-lookup"><span data-stu-id="109c3-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="109c3-120">На момент написания этой статьи, работа, [выполняется](https://github.com/aspnet/Configuration/issues/605) для предоставления этой перегрузки в стандартных .NET и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="109c3-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="109c3-121">Пока AddAzureKeyVault перегрузку, которая принимает данные о наличии сертификата, ASP.NET Core приложения могут обращаться к хранилище ключей Azure с проверкой подлинности на основе сертификата путем явного создания объекта KeyVaultClient, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="109c3-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="109c3-122">В этом примере вызов AddAzureKeyVault поставляется в конце регистрацию поставщика конфигурации.</span><span class="sxs-lookup"><span data-stu-id="109c3-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="109c3-123">Рекомендуется зарегистрировать хранилище ключей Azure в качестве последнего поставщика конфигурации, чтобы он имел возможность переопределения значений конфигурации из предыдущей поставщиков, а не значения конфигурации из других источников переопределяют параметры из хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="109c3-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="109c3-124">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="109c3-124">Additional resources</span></span>

-   <span data-ttu-id="109c3-125">**С помощью хранилища ключей Azure для защиты приложения секреты**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="109c3-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="109c3-126">**Безопасного хранения секрета приложения во время разработки**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="109c3-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="109c3-127">**Настройка защиты данных**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="109c3-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="109c3-128">**Ключ, управления и временем существования**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#-параметров защиты данных — по умолчанию —*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="109c3-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="109c3-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="109c3-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="109c3-130">В репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="109c3-130">GitHub repo.</span></span>
    [<span data-ttu-id="109c3-131">*https://github.com/ASPNET/Configuration/Tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="109c3-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="109c3-132">[Предыдущие] (разработчик app секреты storage.md) [Далее] (.. / takeaways.md ключ)</span><span class="sxs-lookup"><span data-stu-id="109c3-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
