---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901766"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="86711-101">Защита данных. DataProtection.AzureStorage использует новые API службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="86711-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="86711-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> зависит от [библиотек службы хранилища Azure](https://github.com/Azure/azure-storage-net).</span><span class="sxs-lookup"><span data-stu-id="86711-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="86711-103">Эти библиотеки переименовали свои сборки, пакеты и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="86711-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="86711-104">Начиная с ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` использует новые API и пакеты с префиксом `Microsoft.Azure.Storage.`.</span><span class="sxs-lookup"><span data-stu-id="86711-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="86711-105">Если у вас возникли вопросы об API службы хранилища Azure, см. страницу <https://github.com/Azure/azure-storage-net>.</span><span class="sxs-lookup"><span data-stu-id="86711-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="86711-106">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).</span><span class="sxs-lookup"><span data-stu-id="86711-106">For discussion on this issue, see [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="86711-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="86711-107">Version introduced</span></span>

<span data-ttu-id="86711-108">3.0</span><span class="sxs-lookup"><span data-stu-id="86711-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="86711-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="86711-109">Old behavior</span></span>

<span data-ttu-id="86711-110">Пакет ссылался на пакет `WindowsAzure.Storage` NuGet.</span><span class="sxs-lookup"><span data-stu-id="86711-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="86711-111">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="86711-111">New behavior</span></span>

<span data-ttu-id="86711-112">Пакет ссылается на пакет `Microsoft.Azure.Storage.Blob` NuGet.</span><span class="sxs-lookup"><span data-stu-id="86711-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="86711-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="86711-113">Reason for change</span></span>

<span data-ttu-id="86711-114">Это изменение позволяет `Microsoft.AspNetCore.DataProtection.AzureStorage` переходить к рекомендуемым пакетам службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="86711-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="86711-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="86711-115">Recommended action</span></span>

<span data-ttu-id="86711-116">Если вам по-прежнему нужно использовать старые API службы хранилища Azure с ASP.NET Core 3.0, добавьте прямую зависимость в пакет [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/).</span><span class="sxs-lookup"><span data-stu-id="86711-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="86711-117">Этот пакет можно установить вместе с новыми API `Microsoft.Azure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="86711-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="86711-118">Во многих случаях обновление включает только изменение инструкций `using` для использования новых пространств имен:</span><span class="sxs-lookup"><span data-stu-id="86711-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="86711-119">Категория</span><span class="sxs-lookup"><span data-stu-id="86711-119">Category</span></span>

<span data-ttu-id="86711-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="86711-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86711-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="86711-121">Affected APIs</span></span>

<span data-ttu-id="86711-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="86711-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
