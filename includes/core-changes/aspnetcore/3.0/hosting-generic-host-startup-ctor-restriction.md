---
ms.openlocfilehash: be9a79f6ead3e72d7ffaade758704f0c1e2477f0
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394020"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="1e7fd-101">Размещение. Универсальный узел ограничивает внедрение через конструктор Startup</span><span class="sxs-lookup"><span data-stu-id="1e7fd-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="1e7fd-102">Универсальный узел поддерживает для внедрения через конструктор класса `Startup` только типы `IHostEnvironment`, `IWebHostEnvironment` и `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="1e7fd-103">Это не влияет на приложения, которые используют `WebHost`.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1e7fd-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="1e7fd-104">Change description</span></span>

<span data-ttu-id="1e7fd-105">До версии ASP.NET Core 3.0 можно было использовать внедрение конструктора для применения произвольных типов в конструкторе класса `Startup`.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="1e7fd-106">Начиная с ASP.NET Core 3.0 веб-стек переведен на универсальную библиотеку узлов.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="1e7fd-107">Эти изменения можно увидеть в файле *Program.cs* следующих шаблонов:</span><span class="sxs-lookup"><span data-stu-id="1e7fd-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="1e7fd-108">**ASP.NET Core 2.x:**</span><span class="sxs-lookup"><span data-stu-id="1e7fd-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/aspnet/AspNetCore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="1e7fd-109">**ASP.NET Core 3.0:**</span><span class="sxs-lookup"><span data-stu-id="1e7fd-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/aspnet/AspNetCore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="1e7fd-110">`Host` использует контейнер внедрения зависимостей для сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="1e7fd-111">`WebHost` использует два контейнера: один для узла и один для приложения.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="1e7fd-112">В результате конструктор `Startup` теперь не поддерживает внедрение пользовательской службы.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="1e7fd-113">Можно внедрять только `IHostEnvironment`, `IWebHostEnvironment` или `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="1e7fd-114">Это изменение предотвращает такие проблемы, как дублирование создания одноэлементной службы.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1e7fd-115">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="1e7fd-115">Version introduced</span></span>

<span data-ttu-id="1e7fd-116">3.0</span><span class="sxs-lookup"><span data-stu-id="1e7fd-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1e7fd-117">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="1e7fd-117">Reason for change</span></span>

<span data-ttu-id="1e7fd-118">Это изменение является следствием перевода веб-стека на универсальную библиотеку узлов.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1e7fd-119">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="1e7fd-119">Recommended action</span></span>

<span data-ttu-id="1e7fd-120">Внедряйте службы в подпись метода `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="1e7fd-121">Например:</span><span class="sxs-lookup"><span data-stu-id="1e7fd-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="1e7fd-122">Категория</span><span class="sxs-lookup"><span data-stu-id="1e7fd-122">Category</span></span>

<span data-ttu-id="1e7fd-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1e7fd-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1e7fd-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1e7fd-124">Affected APIs</span></span>

<span data-ttu-id="1e7fd-125">Нет</span><span class="sxs-lookup"><span data-stu-id="1e7fd-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
