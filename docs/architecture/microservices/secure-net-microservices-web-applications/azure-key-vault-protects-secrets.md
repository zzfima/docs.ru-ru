---
title: Использование Azure Key Vault для защиты секретов в рабочей среде
description: Безопасность в микрослужбах и веб-приложениях .NET. Azure Key Vault предоставляет отличный способ работы с секретами приложений, которыми полностью управляют администраторы. Администраторы даже могут назначать и отзывать значения разработки без необходимости привлекать к этому разработчиков.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: cc95d491136c945255408cec2bd49d4d6579e29a
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501752"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="478dc-104">Защиты секретов в рабочей среде с помощью Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="478dc-104">Use Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="478dc-105">Секреты, которые сохраняются в переменных среды или с помощью диспетчера секретов, хранятся на компьютере в локальном и незашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="478dc-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="478dc-106">Более безопасный способ хранения секретов — хранилище [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), которое предоставляет безопасное централизованное расположение для хранения ключей и секретов.</span><span class="sxs-lookup"><span data-stu-id="478dc-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="478dc-107">С помощью пакета **Microsoft.Extensions.Configuration.AzureKeyVault** приложение ASP.NET Core может считывать сведения о конфигурации из Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="478dc-107">The **Microsoft.Extensions.Configuration.AzureKeyVault** package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="478dc-108">Чтобы приступить к работе с секретами из Azure Key Vault, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="478dc-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

1. <span data-ttu-id="478dc-109">Зарегистрируйте свое приложение как приложение Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="478dc-109">Register your application as an Azure AD application.</span></span> <span data-ttu-id="478dc-110">(Доступом к хранилищам ключей управляет Azure AD.) Это можно сделать с помощью портала управления Azure.</span><span class="sxs-lookup"><span data-stu-id="478dc-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.\</span></span>

   <span data-ttu-id="478dc-111">Кроме того, если приложение должно проходить проверку подлинности на основе сертификата, а не пароля или секрета клиента, вы можете использовать командлет PowerShell [New-AzADApplication](/powershell/module/az.resources/new-azadapplication).</span><span class="sxs-lookup"><span data-stu-id="478dc-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="478dc-112">Для сертификата, который зарегистрирован в хранилище ключей Azure Key Vault, необходим только ваш открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="478dc-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="478dc-113">Приложение будет использовать закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="478dc-113">Your application will use the private key.</span></span>

2. <span data-ttu-id="478dc-114">Предоставьте зарегистрированному приложению доступ к хранилищу ключей, создав новый субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="478dc-114">Give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="478dc-115">Это можно сделать с помощью следующих команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="478dc-115">You can do this using the following PowerShell commands:</span></span>

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. <span data-ttu-id="478dc-116">Включите в свое приложение хранилище ключей как источник конфигурации. Для этого вызовите метод расширения <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> при создании экземпляра <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>.</span><span class="sxs-lookup"><span data-stu-id="478dc-116">Include the key vault as a configuration source in your application by calling the <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> extension method when you create an <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instance.</span></span> <span data-ttu-id="478dc-117">Обратите внимание, что для вызова метода `AddAzureKeyVault` потребуется идентификатор приложения, которое было зарегистрировано и которому был предоставлен доступ к хранилищу ключей на предыдущих шагах.</span><span class="sxs-lookup"><span data-stu-id="478dc-117">Note that calling `AddAzureKeyVault` requires the application ID that was registered and given access to the key vault in the previous steps.</span></span>

   <span data-ttu-id="478dc-118">Также можно использовать перегрузку метода `AddAzureKeyVault`, который принимает сертификат вместо секрета клиента. Для этого достаточно добавить ссылку на пакет [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory).</span><span class="sxs-lookup"><span data-stu-id="478dc-118">You can also use an overload of `AddAzureKeyVault` that takes a certificate in place of the client secret by just including a reference to the [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="478dc-119">Рекомендуем зарегистрировать Azure Key Vault в качестве последнего поставщика конфигурации, чтобы можно было переопределять значения параметров конфигурации от предыдущих поставщиков.</span><span class="sxs-lookup"><span data-stu-id="478dc-119">We recommend that you register Azure Key Vault as the last configuration provider, so it can override configuration values from previous providers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="478dc-120">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="478dc-120">Additional resources</span></span>

- <span data-ttu-id="478dc-121">**Использование Azure Key Vault для защиты секретов приложений** </span><span class="sxs-lookup"><span data-stu-id="478dc-121">**Using Azure Key Vault to protect application secrets** </span></span>\
  [https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault](/azure/guidance/guidance-multitenant-identity-keyvault)

- <span data-ttu-id="478dc-122">**Безопасное хранение секретов приложения во время разработки** </span><span class="sxs-lookup"><span data-stu-id="478dc-122">**Safe storage of app secrets during development** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- <span data-ttu-id="478dc-123">**Настройка защиты данных** </span><span class="sxs-lookup"><span data-stu-id="478dc-123">**Configuring data protection** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- <span data-ttu-id="478dc-124">**Управление ключами для защиты данных и время существования в ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="478dc-124">**Data Protection key management and lifetime in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- <span data-ttu-id="478dc-125">Репозиторий GitHub **Microsoft.Extensions.Configuration.KeyPerFile**.</span><span class="sxs-lookup"><span data-stu-id="478dc-125">**Microsoft.Extensions.Configuration.KeyPerFile** GitHub repository.</span></span> \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration/Config.KeyPerFile>

>[!div class="step-by-step"]
><span data-ttu-id="478dc-126">[Назад](developer-app-secrets-storage.md)
>[Вперед](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="478dc-126">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
