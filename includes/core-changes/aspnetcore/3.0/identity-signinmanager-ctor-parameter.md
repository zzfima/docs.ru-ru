---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901992"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="967a5-101">Удостоверение. конструктор SignInManager принимает новый параметр</span><span class="sxs-lookup"><span data-stu-id="967a5-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="967a5-102">Начиная с ASP.NET Core 3.0 в конструктор `SignInManager` был добавлен новый параметр `IUserConfirmation<TUser>`.</span><span class="sxs-lookup"><span data-stu-id="967a5-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="967a5-103">Подробную информацию см. на странице [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="967a5-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="967a5-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="967a5-104">Version introduced</span></span>

<span data-ttu-id="967a5-105">3.0</span><span class="sxs-lookup"><span data-stu-id="967a5-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="967a5-106">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="967a5-106">Reason for change</span></span>

<span data-ttu-id="967a5-107">Изменение позволит добавить поддержку новых потоков сообщений электронной почты и подтверждений в удостоверении.</span><span class="sxs-lookup"><span data-stu-id="967a5-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="967a5-108">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="967a5-108">Recommended action</span></span>

<span data-ttu-id="967a5-109">При создании `SignInManager` вручную предоставьте реализацию `IUserConfirmation` или воспользуйтесь реализацией из внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="967a5-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="967a5-110">Категория</span><span class="sxs-lookup"><span data-stu-id="967a5-110">Category</span></span>

<span data-ttu-id="967a5-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="967a5-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="967a5-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="967a5-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
