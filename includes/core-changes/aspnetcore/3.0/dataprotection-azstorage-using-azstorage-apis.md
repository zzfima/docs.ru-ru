---
ms.openlocfilehash: f103c96588bae167216d09a82973a4a7abfb5cc3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394042"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="78a3c-101">Защита данных. DataProtection.AzureStorage использует новые API службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="78a3c-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="78a3c-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> зависит от [библиотек службы хранилища Azure](https://github.com/Azure/azure-storage-net).</span><span class="sxs-lookup"><span data-stu-id="78a3c-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="78a3c-103">Эти библиотеки переименовали свои сборки, пакеты и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="78a3c-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="78a3c-104">Начиная с ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` использует новые API и пакеты с префиксом `Microsoft.Azure.Storage.`.</span><span class="sxs-lookup"><span data-stu-id="78a3c-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="78a3c-105">Если у вас возникли вопросы об API службы хранилища Azure, см. страницу <https://github.com/Azure/azure-storage-net>.</span><span class="sxs-lookup"><span data-stu-id="78a3c-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="78a3c-106">Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).</span><span class="sxs-lookup"><span data-stu-id="78a3c-106">For discussion on this issue, see [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="78a3c-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="78a3c-107">Version introduced</span></span>

<span data-ttu-id="78a3c-108">3.0</span><span class="sxs-lookup"><span data-stu-id="78a3c-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="78a3c-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="78a3c-109">Old behavior</span></span>

<span data-ttu-id="78a3c-110">Пакет ссылался на пакет `WindowsAzure.Storage` NuGet.</span><span class="sxs-lookup"><span data-stu-id="78a3c-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="78a3c-111">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="78a3c-111">New behavior</span></span>

<span data-ttu-id="78a3c-112">Пакет ссылается на пакет `Microsoft.Azure.Storage.Blob` NuGet.</span><span class="sxs-lookup"><span data-stu-id="78a3c-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="78a3c-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="78a3c-113">Reason for change</span></span>

<span data-ttu-id="78a3c-114">Это изменение позволяет `Microsoft.AspNetCore.DataProtection.AzureStorage` переходить к рекомендуемым пакетам службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="78a3c-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="78a3c-115">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="78a3c-115">Recommended action</span></span>

<span data-ttu-id="78a3c-116">Если вам по-прежнему нужно использовать старые API службы хранилища Azure с ASP.NET Core 3.0, добавьте прямую зависимость в пакет [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/).</span><span class="sxs-lookup"><span data-stu-id="78a3c-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="78a3c-117">Этот пакет можно установить вместе с новыми API `Microsoft.Azure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="78a3c-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="78a3c-118">Во многих случаях обновление включает только изменение инструкций `using` для использования новых пространств имен:</span><span class="sxs-lookup"><span data-stu-id="78a3c-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="78a3c-119">Категория</span><span class="sxs-lookup"><span data-stu-id="78a3c-119">Category</span></span>

<span data-ttu-id="78a3c-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="78a3c-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="78a3c-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="78a3c-121">Affected APIs</span></span>

<span data-ttu-id="78a3c-122">Нет</span><span class="sxs-lookup"><span data-stu-id="78a3c-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
