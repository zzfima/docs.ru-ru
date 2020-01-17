---
ms.openlocfilehash: 60ebcd9fc9ca18c33d31b82ba5020426d22a7d5a
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901809"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="fffab-101">Аутентификация. Удаление свойства HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="fffab-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="fffab-102">Устаревшее свойство `Authentication` в `HttpContext` было удалено.</span><span class="sxs-lookup"><span data-stu-id="fffab-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fffab-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="fffab-103">Change description</span></span>

<span data-ttu-id="fffab-104">В рамках [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504) устаревшее свойство `Authentication` в `HttpContext` было удалено.</span><span class="sxs-lookup"><span data-stu-id="fffab-104">As part of [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="fffab-105">Свойство `Authentication` не рекомендуется к использованию, начиная с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="fffab-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="fffab-106">Были опубликованы [инструкции по переносу кода](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) с использованием этого устаревшего свойства в новые API замены.</span><span class="sxs-lookup"><span data-stu-id="fffab-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="fffab-107">Оставшиеся неиспользуемые классы и API, относящиеся к старому стеку проверки подлинности ASP.NET Core 1.x, были удалены в фиксации [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span><span class="sxs-lookup"><span data-stu-id="fffab-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span></span>

<span data-ttu-id="fffab-108">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span><span class="sxs-lookup"><span data-stu-id="fffab-108">For discussion, see [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fffab-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="fffab-109">Version introduced</span></span>

<span data-ttu-id="fffab-110">3.0</span><span class="sxs-lookup"><span data-stu-id="fffab-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="fffab-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="fffab-111">Reason for change</span></span>

<span data-ttu-id="fffab-112">ASP.NET Core API 1.0 были заменены методами расширения в <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="fffab-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fffab-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="fffab-113">Recommended action</span></span>

<span data-ttu-id="fffab-114">См. [руководство по переносу](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span><span class="sxs-lookup"><span data-stu-id="fffab-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="fffab-115">Категория</span><span class="sxs-lookup"><span data-stu-id="fffab-115">Category</span></span>

<span data-ttu-id="fffab-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fffab-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fffab-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="fffab-117">Affected APIs</span></span>

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
