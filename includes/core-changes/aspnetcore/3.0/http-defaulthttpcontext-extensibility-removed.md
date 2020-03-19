---
ms.openlocfilehash: 9d138f79fcede4acac837f8d7793aa343ced737c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78290731"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="e5dfa-101">HTTP. Удаление расширяемости DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="e5dfa-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="e5dfa-102">В рамках повышения производительности ASP.NET Core 3.0 расширяемость `DefaultHttpContext` была удалена.</span><span class="sxs-lookup"><span data-stu-id="e5dfa-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="e5dfa-103">Теперь класс является `sealed`.</span><span class="sxs-lookup"><span data-stu-id="e5dfa-103">The class is now `sealed`.</span></span> <span data-ttu-id="e5dfa-104">Подробную информацию см. на странице [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span><span class="sxs-lookup"><span data-stu-id="e5dfa-104">For more information, see [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span></span>

<span data-ttu-id="e5dfa-105">Если модульные тесты используют `Mock<DefaultHttpContext>`, используйте вместо этого `Mock<HttpContext>` или `new DefaultHttpContext()`.</span><span class="sxs-lookup"><span data-stu-id="e5dfa-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` or `new DefaultHttpContext()` instead.</span></span>

<span data-ttu-id="e5dfa-106">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span><span class="sxs-lookup"><span data-stu-id="e5dfa-106">For discussion, see [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e5dfa-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e5dfa-107">Version introduced</span></span>

<span data-ttu-id="e5dfa-108">3.0</span><span class="sxs-lookup"><span data-stu-id="e5dfa-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e5dfa-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="e5dfa-109">Old behavior</span></span>

<span data-ttu-id="e5dfa-110">Классы могут быть производными от `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="e5dfa-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e5dfa-111">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="e5dfa-111">New behavior</span></span>

<span data-ttu-id="e5dfa-112">Классы не могут быть производными от `DefaultHttpContext`.</span><span class="sxs-lookup"><span data-stu-id="e5dfa-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e5dfa-113">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="e5dfa-113">Reason for change</span></span>

<span data-ttu-id="e5dfa-114">Изначально была предоставлена расширяемость, позволяющая выполнять группировку `HttpContext`, но в ней появились ненужные сложности и другие нарушения, влияющие на оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="e5dfa-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e5dfa-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="e5dfa-115">Recommended action</span></span>

<span data-ttu-id="e5dfa-116">Если вы используете `Mock<DefaultHttpContext>` в модульных тестах, используйте вместо этого `Mock<HttpContext>`.</span><span class="sxs-lookup"><span data-stu-id="e5dfa-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="e5dfa-117">Категория</span><span class="sxs-lookup"><span data-stu-id="e5dfa-117">Category</span></span>

<span data-ttu-id="e5dfa-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e5dfa-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e5dfa-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e5dfa-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
