---
ms.openlocfilehash: 74b989a2413d2192f7cf5208e400eaed879ea096
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198545"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="23132-101">Авторизация: Требование нового метода для реализаций IAuthorizationPolicyProvider</span><span class="sxs-lookup"><span data-stu-id="23132-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="23132-102">В ASP.NET Core 3.0 в `IAuthorizationPolicyProvider` был добавлен новый метод `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="23132-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="23132-103">Эта политика отката используется ПО промежуточного слоя для авторизации, если не указана другая политика.</span><span class="sxs-lookup"><span data-stu-id="23132-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="23132-104">Подробную информацию см. на странице [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="23132-104">For more information, see [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="23132-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="23132-105">Version introduced</span></span>

<span data-ttu-id="23132-106">3.0</span><span class="sxs-lookup"><span data-stu-id="23132-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="23132-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="23132-107">Old behavior</span></span>

<span data-ttu-id="23132-108">Реализации `IAuthorizationPolicyProvider` не требовали метод `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="23132-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="23132-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="23132-109">New behavior</span></span>

<span data-ttu-id="23132-110">Реализации `IAuthorizationPolicyProvider` требуют метод `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="23132-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="23132-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="23132-111">Reason for change</span></span>

<span data-ttu-id="23132-112">Новый метод требуется для использования нового ПО `AuthorizationMiddleware`, если политика не указана.</span><span class="sxs-lookup"><span data-stu-id="23132-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="23132-113">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="23132-113">Recommended action</span></span>

<span data-ttu-id="23132-114">Добавьте метод `GetFallbackPolicyAsync` в реализации `IAuthorizationPolicyProvider`.</span><span class="sxs-lookup"><span data-stu-id="23132-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="23132-115">Категория</span><span class="sxs-lookup"><span data-stu-id="23132-115">Category</span></span>

<span data-ttu-id="23132-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="23132-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="23132-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="23132-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
