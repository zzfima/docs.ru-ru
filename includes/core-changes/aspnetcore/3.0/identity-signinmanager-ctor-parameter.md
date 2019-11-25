---
ms.openlocfilehash: 56b394c4698f60baeb70d3c17d1abee5d867deb7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394083"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="f9073-101">Удостоверение: конструктор SignInManager принимает новый параметр</span><span class="sxs-lookup"><span data-stu-id="f9073-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="f9073-102">Начиная с ASP.NET Core 3.0 в конструктор `SignInManager` был добавлен новый параметр `IUserConfirmation<TUser>`.</span><span class="sxs-lookup"><span data-stu-id="f9073-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="f9073-103">Подробную информацию см. на странице [aspnet/AspNetCore#8356](https://github.com/aspnet/AspNetCore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="f9073-103">For more information, see [aspnet/AspNetCore#8356](https://github.com/aspnet/AspNetCore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f9073-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="f9073-104">Version introduced</span></span>

<span data-ttu-id="f9073-105">3.0</span><span class="sxs-lookup"><span data-stu-id="f9073-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f9073-106">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="f9073-106">Reason for change</span></span>

<span data-ttu-id="f9073-107">Изменение позволит добавить поддержку новых потоков сообщений электронной почты и подтверждений в удостоверении.</span><span class="sxs-lookup"><span data-stu-id="f9073-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f9073-108">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="f9073-108">Recommended action</span></span>

<span data-ttu-id="f9073-109">При создании `SignInManager` вручную предоставьте реализацию `IUserConfirmation` или воспользуйтесь реализацией из внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="f9073-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="f9073-110">Категория</span><span class="sxs-lookup"><span data-stu-id="f9073-110">Category</span></span>

<span data-ttu-id="f9073-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f9073-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f9073-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f9073-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
