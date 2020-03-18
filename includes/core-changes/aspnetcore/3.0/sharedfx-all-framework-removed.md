---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394438"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a><span data-ttu-id="0ee18-101">Общая платформа. Удаление Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="0ee18-101">Shared framework: Removed Microsoft.AspNetCore.All</span></span>

<span data-ttu-id="0ee18-102">Начиная с ASP.NET Core 3.0, метапакет `Microsoft.AspNetCore.All` и соответствующая общая платформа `Microsoft.AspNetCore.All` больше не создаются.</span><span class="sxs-lookup"><span data-stu-id="0ee18-102">Starting in ASP.NET Core 3.0, the `Microsoft.AspNetCore.All` metapackage and the matching `Microsoft.AspNetCore.All` shared framework are no longer produced.</span></span> <span data-ttu-id="0ee18-103">Этот пакет доступен в ASP.NET Core 2.2 и по-прежнему будет принимать обновления для обслуживания в ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="0ee18-103">This package is available in ASP.NET Core 2.2 and will continue to receive servicing updates in ASP.NET Core 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0ee18-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="0ee18-104">Version introduced</span></span>

<span data-ttu-id="0ee18-105">3.0</span><span class="sxs-lookup"><span data-stu-id="0ee18-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0ee18-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="0ee18-106">Old behavior</span></span>

<span data-ttu-id="0ee18-107">Приложения могут использовать метапакет `Microsoft.AspNetCore.All` для целевой общей платформы `Microsoft.AspNetCore.All` в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0ee18-107">Apps could use the `Microsoft.AspNetCore.All` metapackage to target the `Microsoft.AspNetCore.All` shared framework on .NET Core.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0ee18-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="0ee18-108">New behavior</span></span>

<span data-ttu-id="0ee18-109">.NET Core 3.0 не содержит общую платформу `Microsoft.AspNetCore.All`.</span><span class="sxs-lookup"><span data-stu-id="0ee18-109">.NET Core 3.0 doesn't include a `Microsoft.AspNetCore.All` shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0ee18-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="0ee18-110">Reason for change</span></span>

<span data-ttu-id="0ee18-111">Метапакет `Microsoft.AspNetCore.All` включал большое количество внешних зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0ee18-111">The `Microsoft.AspNetCore.All` metapackage included a large number of external dependencies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0ee18-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="0ee18-112">Recommended action</span></span>

<span data-ttu-id="0ee18-113">Перенесите проект для использования платформы `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="0ee18-113">Migrate your project to use the `Microsoft.AspNetCore.App` framework.</span></span> <span data-ttu-id="0ee18-114">Компоненты, которые ранее были доступны в `Microsoft.AspNetCore.All`, по-прежнему будут доступными в NuGet.</span><span class="sxs-lookup"><span data-stu-id="0ee18-114">Components that were previously available in `Microsoft.AspNetCore.All` are still available on NuGet.</span></span> <span data-ttu-id="0ee18-115">Теперь эти компоненты развертываются вместе с приложением, а не включаются в общую платформу.</span><span class="sxs-lookup"><span data-stu-id="0ee18-115">Those components are now deployed with your app instead of being included in the shared framework.</span></span>

#### <a name="category"></a><span data-ttu-id="0ee18-116">Категория</span><span class="sxs-lookup"><span data-stu-id="0ee18-116">Category</span></span>

<span data-ttu-id="0ee18-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0ee18-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0ee18-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0ee18-118">Affected APIs</span></span>

<span data-ttu-id="0ee18-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0ee18-119">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
