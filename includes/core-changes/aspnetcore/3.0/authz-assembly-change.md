---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74101412"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="3c97a-101">Авторизация. Перемещение перегрузки AddAuthorization в другую сборку</span><span class="sxs-lookup"><span data-stu-id="3c97a-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="3c97a-102">Основные методы `AddAuthorization`, используемые для размещения в `Microsoft.AspNetCore.Authorization`, были переименованы в `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="3c97a-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="3c97a-103">Старые методы `AddAuthorization` по-прежнему существуют, но теперь находятся в сборке `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="3c97a-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="3c97a-104">Это не должно повлиять на приложения, использующие оба метода.</span><span class="sxs-lookup"><span data-stu-id="3c97a-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="3c97a-105">Обратите внимание, что `Microsoft.AspNetCore.Authorization.Policy` теперь поставляется в общей платформе, а не в автономном пакете, как описано в разделе [Общая платформа. Из Microsoft.AspNetCore.App удалены сборки](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="3c97a-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3c97a-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="3c97a-106">Version introduced</span></span>

<span data-ttu-id="3c97a-107">3.0</span><span class="sxs-lookup"><span data-stu-id="3c97a-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3c97a-108">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="3c97a-108">Old behavior</span></span>
<span data-ttu-id="3c97a-109">Методы `AddAuthorization` существовали в `Microsoft.AspNetCore.Authorization`.</span><span class="sxs-lookup"><span data-stu-id="3c97a-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3c97a-110">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="3c97a-110">New behavior</span></span>

<span data-ttu-id="3c97a-111">Методы `AddAuthorization` существуют в `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="3c97a-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="3c97a-112">`AddAuthorizationCore` — это новое имя старых методов.</span><span class="sxs-lookup"><span data-stu-id="3c97a-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3c97a-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="3c97a-113">Reason for change</span></span>

<span data-ttu-id="3c97a-114">`AddAuthorization` — это лучшее имя метода для добавления всех общих служб, требуемых для авторизации.</span><span class="sxs-lookup"><span data-stu-id="3c97a-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3c97a-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="3c97a-115">Recommended action</span></span>

<span data-ttu-id="3c97a-116">Добавьте ссылку на `Microsoft.AspNetCore.Authorization.Policy` или используйте вместо этого `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="3c97a-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="3c97a-117">Категория</span><span class="sxs-lookup"><span data-stu-id="3c97a-117">Category</span></span>

<span data-ttu-id="3c97a-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c97a-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3c97a-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3c97a-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
