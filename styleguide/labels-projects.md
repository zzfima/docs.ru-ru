---
ms.openlocfilehash: 99153bb9cf3287951a1e52e716c799ee64eb82ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78950991"
---
# <a name="labels-and-projects-roadmap"></a><span data-ttu-id="a3385-101">Стратегия применения меток и проектов</span><span class="sxs-lookup"><span data-stu-id="a3385-101">Labels and projects roadmap</span></span>

<span data-ttu-id="a3385-102">Группа по работе с документацией по .NET широко применяет в своей работе [метки GitHub](https://github.com/dotnet/docs/labels).</span><span class="sxs-lookup"><span data-stu-id="a3385-102">The .NET docs team makes extensive use of [GitHub labels](https://github.com/dotnet/docs/labels) to organize our work.</span></span> <span data-ttu-id="a3385-103">Фильтрами по комбинациям меток мы можем быстро выбрать интересующие нас разделы на [веб-сайте документации по .NET](https://docs.microsoft.com/dotnet).</span><span class="sxs-lookup"><span data-stu-id="a3385-103">By filtering on combinations of labels, we can quickly focus on sections of interest on the [.NET docs website](https://docs.microsoft.com/dotnet).</span></span>

<span data-ttu-id="a3385-104">Мы также используем [проекты GitHub](https://github.com/dotnet/docs/projects) для организации спринтов и других групп задач для достижения конкретной цели.</span><span class="sxs-lookup"><span data-stu-id="a3385-104">We also use [GitHub projects](https://github.com/dotnet/docs/projects) to organize sprints and other goal-oriented epics.</span></span>

<span data-ttu-id="a3385-105">В этой стратегии объясняется, как мы используем эти организационные средства, а также есть ссылки на удобные фильтры по некоторым важным областям.</span><span class="sxs-lookup"><span data-stu-id="a3385-105">This roadmap explains how we use these organizational tools and has links to handy filters we use to find areas of interest.</span></span>

## <a name="labels"></a><span data-ttu-id="a3385-106">Подписи</span><span class="sxs-lookup"><span data-stu-id="a3385-106">Labels</span></span>

<span data-ttu-id="a3385-107">Если вы впервые участвуете в работе c [dotnet/docs](https://github.com/dotnet/docs), начните со списка проблем [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs).</span><span class="sxs-lookup"><span data-stu-id="a3385-107">If this is your first experience contributing to [dotnet/docs](https://github.com/dotnet/docs), start with the [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) issues.</span></span> <span data-ttu-id="a3385-108">В него включены проблемы с довольно узкой областью.</span><span class="sxs-lookup"><span data-stu-id="a3385-108">These are issues that have a more focused scope.</span></span> <span data-ttu-id="a3385-109">Это отличный путь для первого вклада в работу.</span><span class="sxs-lookup"><span data-stu-id="a3385-109">They are a great way to make your first contribution.</span></span> <span data-ttu-id="a3385-110">В представлении "up-for-grabs" вы можете отфильтровать проблемы по областям и приоритетам.</span><span class="sxs-lookup"><span data-stu-id="a3385-110">From the up-for-grabs view, you can further filter issues based on areas and priority.</span></span> <span data-ttu-id="a3385-111">Проблемы, которые хорошо подходят для начинающих, мы обозначаем меткой [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue), и они помогут вам внести первый небольшой вклад.</span><span class="sxs-lookup"><span data-stu-id="a3385-111">We've identified good issues for beginners with the [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) if you want to try a smaller first contribution.</span></span>

<span data-ttu-id="a3385-112">Мы используем метки для классификации проблем несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="a3385-112">We use labels to classify issues in many different ways:</span></span>

- <span data-ttu-id="a3385-113">[руководства по .NET](#find-a-single-net-guide) и [разделы руководства](#search-one-section-of-a-guide);</span><span class="sxs-lookup"><span data-stu-id="a3385-113">[.NET Guides](#find-a-single-net-guide) and [sections of a guide](#search-one-section-of-a-guide).</span></span>
- <span data-ttu-id="a3385-114">[целевые выпуски](#releases);</span><span class="sxs-lookup"><span data-stu-id="a3385-114">[Target release](#releases)</span></span>
- [<span data-ttu-id="a3385-115">Приоритет</span><span class="sxs-lookup"><span data-stu-id="a3385-115">Priority</span></span>](#priority)

<span data-ttu-id="a3385-116">Объединяя метки из каждого набора (руководство, выпуск, приоритет), вы можете создать узкие срезы для поиска проблем, с которыми вы намерены работать.</span><span class="sxs-lookup"><span data-stu-id="a3385-116">You can combine a label from each set (guide, release, priority) to create a narrow focus to find issues you want to work on.</span></span>

### <a name="find-a-single-net-guide"></a><span data-ttu-id="a3385-117">Поиск конкретного руководства по .NET</span><span class="sxs-lookup"><span data-stu-id="a3385-117">Find a single .NET guide</span></span>

<span data-ttu-id="a3385-118">Мы используем метки для каждой из электронных книг по архитектуре и для каждого руководства по .NET.</span><span class="sxs-lookup"><span data-stu-id="a3385-118">We use labels for each of the architecture e-books and for each .NET Guide.</span></span>

<span data-ttu-id="a3385-119">![:book: руководство на светло-зеленом фоне](./images/guide.png "Префикс для меток руководств по архитектуре")</span><span class="sxs-lookup"><span data-stu-id="a3385-119">![:book: guide on light green background](./images/guide.png "Prefix for architecture guide labels")</span></span>

<span data-ttu-id="a3385-120">Электронные книги по архитектуре обозначаются префиксом `:book: guide` и имеют светло-зеленый фон.</span><span class="sxs-lookup"><span data-stu-id="a3385-120">Architecture e-books are noted with the `:book: guide` prefix and have a light green background.</span></span> <span data-ttu-id="a3385-121">Это развернутые описания, относящиеся к рекомендуемой архитектуре.</span><span class="sxs-lookup"><span data-stu-id="a3385-121">These are the long-form areas that cover recommended architecture.</span></span> <span data-ttu-id="a3385-122">Вот пример списка текущих проблем, которые отфильтрованы по каждому из руководств по архитектуре .NET.</span><span class="sxs-lookup"><span data-stu-id="a3385-122">Here are current issues filtered for each of the .NET architecture guides.</span></span>

- [<span data-ttu-id="a3385-123">Веб-приложения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a3385-123">ASP.NET Core web apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [<span data-ttu-id="a3385-124">Blazor</span><span class="sxs-lookup"><span data-stu-id="a3385-124">Blazor</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [<span data-ttu-id="a3385-125">Полностью облачные</span><span class="sxs-lookup"><span data-stu-id="a3385-125">Cloud Native</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [<span data-ttu-id="a3385-126">Жизненный цикл Docker</span><span class="sxs-lookup"><span data-stu-id="a3385-126">Docker lifecycle</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [<span data-ttu-id="a3385-127">gRPC</span><span class="sxs-lookup"><span data-stu-id="a3385-127">gRPC</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [<span data-ttu-id="a3385-128">Модернизация с помощью контейнеров Windows</span><span class="sxs-lookup"><span data-stu-id="a3385-128">Modernizing w/ Windows containers</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [<span data-ttu-id="a3385-129">Микрослужбы .NET</span><span class="sxs-lookup"><span data-stu-id="a3385-129">.NET Microservices</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [<span data-ttu-id="a3385-130">Бессерверные приложения</span><span class="sxs-lookup"><span data-stu-id="a3385-130">Serverless apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

<span data-ttu-id="a3385-131">Этот же стиль меток применяется к [рекомендациям по проектированию платформы](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines).</span><span class="sxs-lookup"><span data-stu-id="a3385-131">This label style is also applied to the [Framework design guidelines](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines).</span></span> <span data-ttu-id="a3385-132">Для этой области используется та же структура меток, но запросы на вытягивание от сообщества здесь не рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="a3385-132">This area has the same label design, but community PRs are discouraged.</span></span> <span data-ttu-id="a3385-133">Эти материалы переиздаются по индивидуальным разрешениям и не должны редактироваться.</span><span class="sxs-lookup"><span data-stu-id="a3385-133">This is material reprinted with permission and should not be edited.</span></span>

<span data-ttu-id="a3385-134">![:books: Область на темно-синем фоне](./images/area.png "Префикс для меток области руководства по .NET")</span><span class="sxs-lookup"><span data-stu-id="a3385-134">![:books: Area on dark blue background](./images/area.png "Prefix for .NET Guide area labels")</span></span>

<span data-ttu-id="a3385-135">Каждое из руководств по .NET обозначено префиксом `:books: Area` и имеет темно-синий фон.</span><span class="sxs-lookup"><span data-stu-id="a3385-135">Each .NET Guide is noted with the `:books: Area` prefix and has a dark blue background.</span></span> <span data-ttu-id="a3385-136">Вот пример списка текущих проблем, которые отфильтрованы по каждому из руководств .NET.</span><span class="sxs-lookup"><span data-stu-id="a3385-136">Here are current issues filtered for each of the .NET guides.</span></span>

- [<span data-ttu-id="a3385-137">Справочник по интерфейсам API</span><span class="sxs-lookup"><span data-stu-id="a3385-137">API Reference</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [<span data-ttu-id="a3385-138">Пакет SDK Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="a3385-138">Azure .NET SDK</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [<span data-ttu-id="a3385-139">Руководство по языку C#</span><span class="sxs-lookup"><span data-stu-id="a3385-139">C# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [<span data-ttu-id="a3385-140">Руководство по классическим приложениям</span><span class="sxs-lookup"><span data-stu-id="a3385-140">Desktop Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [<span data-ttu-id="a3385-141">Руководство по языку F#</span><span class="sxs-lookup"><span data-stu-id="a3385-141">F# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [<span data-ttu-id="a3385-142">Руководство по ML.NET</span><span class="sxs-lookup"><span data-stu-id="a3385-142">ML.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- <span data-ttu-id="a3385-143">[Руководство по архитектуре .NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) — может быть удалено</span><span class="sxs-lookup"><span data-stu-id="a3385-143">[.NET Architecture Guide](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - Could be removed</span></span>
- [<span data-ttu-id="a3385-144">Руководство по .NET Core</span><span class="sxs-lookup"><span data-stu-id="a3385-144">.NET Core Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [<span data-ttu-id="a3385-145">Руководство по .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="a3385-145">.NET for Apache Spark Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [<span data-ttu-id="a3385-146">Руководство по .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a3385-146">.NET Framework Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [<span data-ttu-id="a3385-147">Руководство по .NET</span><span class="sxs-lookup"><span data-stu-id="a3385-147">.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- <span data-ttu-id="a3385-148">[Справочник по API Roslyn](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) — может быть удален.</span><span class="sxs-lookup"><span data-stu-id="a3385-148">[Roslyn API Reference](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - could be removed.</span></span>
- [<span data-ttu-id="a3385-149">Руководство по Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3385-149">Visual Basic Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a><span data-ttu-id="a3385-150">Поиск по одному разделу руководства</span><span class="sxs-lookup"><span data-stu-id="a3385-150">Search one section of a guide</span></span>

<span data-ttu-id="a3385-151">![:card_file_box: Область на светло-синем фоне](./images/technology.png "Префикс для меток вложенных областей руководства по .NET")</span><span class="sxs-lookup"><span data-stu-id="a3385-151">![:card_file_box: Area on medium blue background](./images/technology.png "Prefix for .NET Guide sub-area labels")</span></span>

<span data-ttu-id="a3385-152">Руководства по .NET достаточно большие, а эти метки позволяют дополнительно ограничить область поиска конкретным разделом руководства.</span><span class="sxs-lookup"><span data-stu-id="a3385-152">The .NET guides are large, so these labels further limit the scope by a section of a guide.</span></span> <span data-ttu-id="a3385-153">Каждая из вложенных областей руководств по .NET обозначено префиксом `:card_file_box: Technology` и имеет светло-синий фон.</span><span class="sxs-lookup"><span data-stu-id="a3385-153">Each .NET Guide subarea is noted with the `:card_file_box: Technology` prefix and has a medium blue background.</span></span> <span data-ttu-id="a3385-154">Многие из этих меток применяются к нескольким руководствам, а другие — только к одному из них.</span><span class="sxs-lookup"><span data-stu-id="a3385-154">Many of these labels apply to multiple guides, while others are in only one guide.</span></span> <span data-ttu-id="a3385-155">Применив фильтр по области, добавьте одну из этих меток, чтобы ограничить область поиска проблем.</span><span class="sxs-lookup"><span data-stu-id="a3385-155">After filtering on an area, add one of these labels to further limit the scope of issues.</span></span>

- <span data-ttu-id="a3385-156">AppCompat</span><span class="sxs-lookup"><span data-stu-id="a3385-156">AppCompat</span></span>
- <span data-ttu-id="a3385-157">Асинхронная задача</span><span class="sxs-lookup"><span data-stu-id="a3385-157">Async Task</span></span>
- <span data-ttu-id="a3385-158">Дополнительные возможности C#</span><span class="sxs-lookup"><span data-stu-id="a3385-158">C# Advanced concepts</span></span>
- <span data-ttu-id="a3385-159">Компилятор C#</span><span class="sxs-lookup"><span data-stu-id="a3385-159">C# compiler</span></span>
- <span data-ttu-id="a3385-160">Основы C#</span><span class="sxs-lookup"><span data-stu-id="a3385-160">C# Fundamentals</span></span>
- <span data-ttu-id="a3385-161">Начало работы с C#</span><span class="sxs-lookup"><span data-stu-id="a3385-161">C# Get Started</span></span>
- <span data-ttu-id="a3385-162">Справочник по языку C#</span><span class="sxs-lookup"><span data-stu-id="a3385-162">C# Language Reference</span></span>
- <span data-ttu-id="a3385-163">Безопасность значений NULL в C#</span><span class="sxs-lookup"><span data-stu-id="a3385-163">C# Null safety</span></span>
- <span data-ttu-id="a3385-164">Новые возможности C#</span><span class="sxs-lookup"><span data-stu-id="a3385-164">C# What's new</span></span>
- <span data-ttu-id="a3385-165">CLI</span><span class="sxs-lookup"><span data-stu-id="a3385-165">CLI</span></span>
- <span data-ttu-id="a3385-166">Доступ к данным</span><span class="sxs-lookup"><span data-stu-id="a3385-166">Data Access</span></span>
- <span data-ttu-id="a3385-167">Docker</span><span class="sxs-lookup"><span data-stu-id="a3385-167">Docker</span></span>
- <span data-ttu-id="a3385-168">Установщики</span><span class="sxs-lookup"><span data-stu-id="a3385-168">Installers</span></span>
- <span data-ttu-id="a3385-169">LINQ</span><span class="sxs-lookup"><span data-stu-id="a3385-169">LINQ</span></span>
- <span data-ttu-id="a3385-170">NCL</span><span class="sxs-lookup"><span data-stu-id="a3385-170">NCL</span></span>
- <span data-ttu-id="a3385-171">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="a3385-171">.NET Standard</span></span>
- <span data-ttu-id="a3385-172">API Roslyn</span><span class="sxs-lookup"><span data-stu-id="a3385-172">Roslyn APIs</span></span>
- <span data-ttu-id="a3385-173">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a3385-173">Security</span></span>
- <span data-ttu-id="a3385-174">WCF</span><span class="sxs-lookup"><span data-stu-id="a3385-174">WCF</span></span>
- <span data-ttu-id="a3385-175">WF</span><span class="sxs-lookup"><span data-stu-id="a3385-175">WF</span></span>
- <span data-ttu-id="a3385-176">WIF</span><span class="sxs-lookup"><span data-stu-id="a3385-176">WIF</span></span>
- <span data-ttu-id="a3385-177">WinForms</span><span class="sxs-lookup"><span data-stu-id="a3385-177">WinForms</span></span>
- <span data-ttu-id="a3385-178">WPF</span><span class="sxs-lookup"><span data-stu-id="a3385-178">WPF</span></span>

### <a name="releases"></a><span data-ttu-id="a3385-179">Выпуски</span><span class="sxs-lookup"><span data-stu-id="a3385-179">Releases</span></span>

<span data-ttu-id="a3385-180">![:checkered_flag: Выпуск на темно-желтом фоне](./images/release.png "Префикс для меток выпуска")</span><span class="sxs-lookup"><span data-stu-id="a3385-180">![:checkered_flag: Release: on dark yellow](./images/release.png "Prefix for release labels")</span></span>

<span data-ttu-id="a3385-181">Проблемы, помеченные для конкретного выпуска, обозначаются префиксом `:checkered_flag: Release:` и отображаются на темно-желтом фоне.</span><span class="sxs-lookup"><span data-stu-id="a3385-181">Issues tagged for a specific release are noted with the `:checkered_flag: Release:` prefix and have a dark yellow background.</span></span>

- <span data-ttu-id="a3385-182">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a3385-182">.NET Core 2.2</span></span>
- <span data-ttu-id="a3385-183">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a3385-183">.NET Core 3.0</span></span>

### <a name="priority"></a><span data-ttu-id="a3385-184">Priority</span><span class="sxs-lookup"><span data-stu-id="a3385-184">Priority</span></span>

<span data-ttu-id="a3385-185">Метки приоритета содержат символ `P`, за которым следует одна цифра.</span><span class="sxs-lookup"><span data-stu-id="a3385-185">Priority labels are all `P` followed by a single digit.</span></span> <span data-ttu-id="a3385-186">Чем меньше число, тем выше приоритет.</span><span class="sxs-lookup"><span data-stu-id="a3385-186">Lower numbers are higher priority:</span></span>

- <span data-ttu-id="a3385-187">P0</span><span class="sxs-lookup"><span data-stu-id="a3385-187">P0</span></span>
- <span data-ttu-id="a3385-188">P1</span><span class="sxs-lookup"><span data-stu-id="a3385-188">P1</span></span>
- <span data-ttu-id="a3385-189">P2</span><span class="sxs-lookup"><span data-stu-id="a3385-189">P2</span></span>

### <a name="what-about-the-other-labels"></a><span data-ttu-id="a3385-190">Какие еще бывают метки?</span><span class="sxs-lookup"><span data-stu-id="a3385-190">What about the other labels?</span></span>

<span data-ttu-id="a3385-191">Группы по работе над содержимым используют много других меток для управления разными классификациями проблем.</span><span class="sxs-lookup"><span data-stu-id="a3385-191">There are many other labels used by the content teams to manage different classifications of issues.</span></span> <span data-ttu-id="a3385-192">Если вы не входите в такую группу, остальные метки можно смело игнорировать.</span><span class="sxs-lookup"><span data-stu-id="a3385-192">If you're not on the content team, you can ignore these other labels.</span></span>

## <a name="projects"></a><span data-ttu-id="a3385-193">Проекты</span><span class="sxs-lookup"><span data-stu-id="a3385-193">Projects</span></span>

<span data-ttu-id="a3385-194">Желающим внести вклад следует ознакомиться со статьей [Проекты для участников сообщества .NET](https://github.com/dotnet/docs/projects/35).</span><span class="sxs-lookup"><span data-stu-id="a3385-194">Contributors should check the [Projects for .NET community collaborators](https://github.com/dotnet/docs/projects/35).</span></span> <span data-ttu-id="a3385-195">Мы создали несколько колонок по обслуживанию, обновлению документации и задач по созданию содержимого.</span><span class="sxs-lookup"><span data-stu-id="a3385-195">We've created different columns for maintenance, document updates, and new content tasks.</span></span> <span data-ttu-id="a3385-196">Возможно, так вам будет удобно найти интересные задачи.</span><span class="sxs-lookup"><span data-stu-id="a3385-196">This can be a way to find tasks of interest.</span></span> <span data-ttu-id="a3385-197">(Обратите внимание, что представление проектов можно отфильтровать по описанным выше меткам.)</span><span class="sxs-lookup"><span data-stu-id="a3385-197">(Note that the project view can be filtered using the labels described above.)</span></span>

<span data-ttu-id="a3385-198">У нас есть еще два способа применения проектов.</span><span class="sxs-lookup"><span data-stu-id="a3385-198">We also use projects in two other ways:</span></span>

- <span data-ttu-id="a3385-199">Типы проектов по месяцам и годам. Выполняют роль досок Scrum для рабочего плана по каждому месяцу.</span><span class="sxs-lookup"><span data-stu-id="a3385-199">Month YYYY project types: These are scrum boards for each month's working plan.</span></span>
- <span data-ttu-id="a3385-200">Группы продолжительных задач. Используются для упорядочения задач, направленных на конкретную цель, если общий объем работ рассчитан на нескольких месяцев.</span><span class="sxs-lookup"><span data-stu-id="a3385-200">Long-running epics: These are used to organize tasks toward a goal when the work will occur over several months.</span></span>
