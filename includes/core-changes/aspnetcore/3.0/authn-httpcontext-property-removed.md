---
ms.openlocfilehash: 2945465bb6a3a362dc640641056712dffd73d559
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394264"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="82e51-101">Аутентификация. Удаление свойства HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="82e51-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="82e51-102">Устаревшее свойство `Authentication` в `HttpContext` было удалено.</span><span class="sxs-lookup"><span data-stu-id="82e51-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="82e51-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="82e51-103">Change description</span></span>

<span data-ttu-id="82e51-104">В рамках [ASPNET/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504) устаревшее свойство `Authentication` в `HttpContext` было удалено.</span><span class="sxs-lookup"><span data-stu-id="82e51-104">As part of [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="82e51-105">Свойство `Authentication` не рекомендуется к использованию, начиная с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="82e51-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="82e51-106">Были опубликованы [инструкции по переносу кода](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) с использованием этого устаревшего свойства в новые API замены.</span><span class="sxs-lookup"><span data-stu-id="82e51-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="82e51-107">Оставшиеся неиспользуемые классы и API, относящиеся к старому стеку проверки подлинности ASP.NET Core 1.x, были удалены в фиксации [aspnet/AspNetCore@d7a7c65](https://github.com/aspnet/AspNetCore/commit/d7a7c65).</span><span class="sxs-lookup"><span data-stu-id="82e51-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [aspnet/AspNetCore@d7a7c65](https://github.com/aspnet/AspNetCore/commit/d7a7c65).</span></span>

<span data-ttu-id="82e51-108">Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#6533](https://github.com/aspnet/AspNetCore/issues/6533).</span><span class="sxs-lookup"><span data-stu-id="82e51-108">For discussion, see [aspnet/AspNetCore#6533](https://github.com/aspnet/AspNetCore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="82e51-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="82e51-109">Version introduced</span></span>

<span data-ttu-id="82e51-110">3.0</span><span class="sxs-lookup"><span data-stu-id="82e51-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="82e51-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="82e51-111">Reason for change</span></span>

<span data-ttu-id="82e51-112">ASP.NET Core API 1.0 были заменены методами расширения в <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="82e51-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="82e51-113">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="82e51-113">Recommended action</span></span>

<span data-ttu-id="82e51-114">См. [руководство по переносу](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span><span class="sxs-lookup"><span data-stu-id="82e51-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="82e51-115">Категория</span><span class="sxs-lookup"><span data-stu-id="82e51-115">Category</span></span>

<span data-ttu-id="82e51-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="82e51-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="82e51-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="82e51-117">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
