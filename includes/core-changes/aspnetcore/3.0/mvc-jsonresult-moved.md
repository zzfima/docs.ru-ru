---
ms.openlocfilehash: f6fd75c5b49156f44d31c650ea452eb549f13b0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901873"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="779ed-101">MVC. JsonResult перемещен в Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="779ed-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="779ed-102">`JsonResult` перемещен в сборку `Microsoft.AspNetCore.Mvc.Core`.</span><span class="sxs-lookup"><span data-stu-id="779ed-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="779ed-103">Этот тип используется для определения в [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span><span class="sxs-lookup"><span data-stu-id="779ed-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="779ed-104">Чтобы устранить эту ошибку для большинства пользователей, атрибут уровня сборки [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) добавлен в `Microsoft.AspNetCore.Mvc.Formatters.Json`.</span><span class="sxs-lookup"><span data-stu-id="779ed-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="779ed-105">В приложениях, использующих сторонние библиотеки, могут возникать проблемы.</span><span class="sxs-lookup"><span data-stu-id="779ed-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="779ed-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="779ed-106">Version introduced</span></span>

<span data-ttu-id="779ed-107">6 предварительная версия 3.0</span><span class="sxs-lookup"><span data-stu-id="779ed-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="779ed-108">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="779ed-108">Old behavior</span></span>

<span data-ttu-id="779ed-109">Сборка приложения, использующего библиотеку на основе версии 2.2, проходит успешно.</span><span class="sxs-lookup"><span data-stu-id="779ed-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="779ed-110">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="779ed-110">New behavior</span></span>

<span data-ttu-id="779ed-111">Приложение, использующее библиотеку на основе версии 2.2 не может выполнить компиляцию.</span><span class="sxs-lookup"><span data-stu-id="779ed-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="779ed-112">Указана ошибка, содержащая разновидность следующего текста:</span><span class="sxs-lookup"><span data-stu-id="779ed-112">An error containing a variation of the following text is provided:</span></span>

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="779ed-113">Пример такой проблемы см. в разделе [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span><span class="sxs-lookup"><span data-stu-id="779ed-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="779ed-114">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="779ed-114">Reason for change</span></span>

<span data-ttu-id="779ed-115">Изменения на уровне платформы для композиции ASP.NET Core, как описано в разделе [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span><span class="sxs-lookup"><span data-stu-id="779ed-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="779ed-116">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="779ed-116">Recommended action</span></span>

<span data-ttu-id="779ed-117">Чтобы устранить проблему для всех потребителей, для библиотек, скомпилированных `Microsoft.AspNetCore.Mvc.Formatters.Json` версии 2.2, может потребоваться повторная компиляция.</span><span class="sxs-lookup"><span data-stu-id="779ed-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="779ed-118">Если это произошло, обратитесь к автору библиотеки.</span><span class="sxs-lookup"><span data-stu-id="779ed-118">If affected, contact the library author.</span></span> <span data-ttu-id="779ed-119">Запросите перекомпиляцию библиотеки в целевой ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="779ed-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="779ed-120">Категория</span><span class="sxs-lookup"><span data-stu-id="779ed-120">Category</span></span>

<span data-ttu-id="779ed-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="779ed-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="779ed-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="779ed-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
