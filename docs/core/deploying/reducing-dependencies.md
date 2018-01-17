---
title: "Сокращение зависимостей пакетов с помощью файла project.json"
description: "Сократите зависимости пакетов при создании библиотек на базе project.json."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 916251e3-87f9-4eee-81ec-94076215e6fa
ms.workload: dotnetcore
ms.openlocfilehash: 858fc77d9652bfa59ed0bb3159260f40c76156a4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="reducing-package-dependencies-with-projectjson"></a><span data-ttu-id="93c5f-104">Сокращение зависимостей пакетов с помощью файла project.json</span><span class="sxs-lookup"><span data-stu-id="93c5f-104">Reducing Package Dependencies with project.json</span></span>

<span data-ttu-id="93c5f-105">В этой статье приводятся необходимые сведения о сокращении зависимостей пакетов при разработке библиотек `project.json`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-105">This article covers what you need to know about reducing your package dependencies when authoring `project.json` libraries.</span></span> <span data-ttu-id="93c5f-106">К концу этой статьи вы научитесь составлять библиотеки так, чтобы в них использовались только необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="93c5f-106">By the end of this article, you will learn how to compose your library such that it only uses the dependencies it needs.</span></span> 

## <a name="why-its-important"></a><span data-ttu-id="93c5f-107">Почему это важно</span><span class="sxs-lookup"><span data-stu-id="93c5f-107">Why it's Important</span></span>

<span data-ttu-id="93c5f-108">.NET Core — это продукт, состоящий из пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="93c5f-108">.NET Core is a product made up of NuGet packages.</span></span>  <span data-ttu-id="93c5f-109">Базовый пакет — это [метапакет NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library). Он представляет собой пакет NuGet, состоящий из других пакетов.</span><span class="sxs-lookup"><span data-stu-id="93c5f-109">An essential package is the [.NETStandard.Library metapackage](https://www.nuget.org/packages/NETStandard.Library), which is a NuGet package composed of other packages.</span></span>  <span data-ttu-id="93c5f-110">Этот метапакет предоставляет набор пакетов, которые гарантированно работают в различных реализациях .NET, таких как .NET Framework, .NET Core и Xamarin/Mono.</span><span class="sxs-lookup"><span data-stu-id="93c5f-110">It provides you with the set of packages that are guaranteed to work on multiple .NET implementations, such as .NET Framework, .NET Core and Xamarin/Mono.</span></span>

<span data-ttu-id="93c5f-111">Однако высока вероятность того, что ваша библиотека будет использовать не все входящие в него пакеты.</span><span class="sxs-lookup"><span data-stu-id="93c5f-111">However, there's a good chance that your library won't use every single package it contains.</span></span>  <span data-ttu-id="93c5f-112">При разработке библиотеки и ее распространении посредством NuGet рекомендуется "усекать" зависимости, оставляя только действительно необходимые.</span><span class="sxs-lookup"><span data-stu-id="93c5f-112">When authoring a library and distributing it over NuGet, it's a best practice to "trim" your dependencies down to only the packages you actually use.</span></span>  <span data-ttu-id="93c5f-113">Результатом является уменьшение общего размера пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="93c5f-113">This results in a smaller overall footprint for NuGet packages.</span></span>

## <a name="how-to-do-it"></a><span data-ttu-id="93c5f-114">Как это сделать</span><span class="sxs-lookup"><span data-stu-id="93c5f-114">How to do it</span></span>

<span data-ttu-id="93c5f-115">В настоящее время нет официальной команды `dotnet`, которая усекает ссылки на пакеты.</span><span class="sxs-lookup"><span data-stu-id="93c5f-115">Currently, there is no official `dotnet` command which trims package references.</span></span>  <span data-ttu-id="93c5f-116">Вам потребуется сделать это вручную.</span><span class="sxs-lookup"><span data-stu-id="93c5f-116">Instead, you'll have to do it manually.</span></span>  <span data-ttu-id="93c5f-117">Ниже описывается общая процедура:</span><span class="sxs-lookup"><span data-stu-id="93c5f-117">The general process looks like the following:</span></span>

1. <span data-ttu-id="93c5f-118">Укажите ссылку на `NETStandard.Library` версии `1.6.0` в разделе `dependencies` файла `project.json`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-118">Reference `NETStandard.Library` version `1.6.0` in a `dependencies` section of your `project.json`.</span></span>
2. <span data-ttu-id="93c5f-119">Восстановите пакеты, выполнив команду `dotnet restore` ([см. примечание](#dotnet-restore-note)) в командной строке.</span><span class="sxs-lookup"><span data-stu-id="93c5f-119">Restore packages with `dotnet restore` ([see note](#dotnet-restore-note)) from the command line.</span></span>
3. <span data-ttu-id="93c5f-120">Просмотрите файл `project.lock.json` и найдите раздел `NETSTandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-120">Inspect the `project.lock.json` file and find the `NETSTandard.Library` section.</span></span>  <span data-ttu-id="93c5f-121">Он находится ближе к началу файла.</span><span class="sxs-lookup"><span data-stu-id="93c5f-121">It's near the beginning of the file.</span></span>
4. <span data-ttu-id="93c5f-122">Скопируйте все пакеты, перечисленные в разделе `dependencies`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-122">Copy all of the listed packages under `dependencies`.</span></span>
5. <span data-ttu-id="93c5f-123">Удалите ссылку на `.NETStandard.Library` и замените ее скопированными пакетами.</span><span class="sxs-lookup"><span data-stu-id="93c5f-123">Remove the `.NETStandard.Library` reference and replace it with the copied packages.</span></span>
6. <span data-ttu-id="93c5f-124">Удалите ссылки на пакеты, которые вам не нужны.</span><span class="sxs-lookup"><span data-stu-id="93c5f-124">Remove references to packages you don't need.</span></span>


<span data-ttu-id="93c5f-125">Узнать, какие пакеты вам не нужны, можно одним из указанных ниже способов:</span><span class="sxs-lookup"><span data-stu-id="93c5f-125">You can find out which packages you don't need by one of the following ways:</span></span>

1. <span data-ttu-id="93c5f-126">Методом проб и ошибок.</span><span class="sxs-lookup"><span data-stu-id="93c5f-126">Trial and error.</span></span>  <span data-ttu-id="93c5f-127">То есть вам нужно удалить пакет, выполнить восстановление, проверить, компилируется ли по-прежнему библиотека, а затем повторить этот процесс.</span><span class="sxs-lookup"><span data-stu-id="93c5f-127">This involves removing a package, restoring, seeing if your library still compiles, and repeating this process.</span></span>
2. <span data-ttu-id="93c5f-128">С помощью такого средства, как [ILSpy](http://ilspy.net) или [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector), изучить ссылки, чтобы узнать, какие из них действительно используются в коде.</span><span class="sxs-lookup"><span data-stu-id="93c5f-128">Using a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to peek at references to see what your code is actually using.</span></span>  <span data-ttu-id="93c5f-129">Затем можно удалить пакеты, которые не соответствуют используемым типам.</span><span class="sxs-lookup"><span data-stu-id="93c5f-129">You can then remove packages which don't correspond to types you're using.</span></span>

## <a name="example"></a><span data-ttu-id="93c5f-130">Пример</span><span class="sxs-lookup"><span data-stu-id="93c5f-130">Example</span></span> 

<span data-ttu-id="93c5f-131">Представьте, что вы написали библиотеку, расширяющую функциональность универсальных типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="93c5f-131">Imagine that you wrote a library which provided additional functionality to generic collection types.</span></span>  <span data-ttu-id="93c5f-132">Подобная библиотека обязательно будет зависеть от таких пакетов, как `System.Collections`, но может совершенно не использовать такие пакеты, как `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-132">Such a library would need to depend on packages such as `System.Collections`, but may not at all depend on packages such as `System.Net.Http`.</span></span>  <span data-ttu-id="93c5f-133">Поэтому было бы неплохо ограничить зависимости пакетов только теми, которые действительно требуются библиотеке.</span><span class="sxs-lookup"><span data-stu-id="93c5f-133">As such, it would be good to trim package dependencies down to only what this library required!</span></span>

<span data-ttu-id="93c5f-134">Чтобы усечь зависимости в этой библиотеке, необходимо начать с файла `project.json` и добавить ссылку на `NETStandard.Library` версии `1.6.0`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-134">To trim this library, you start with the `project.json` file and add a reference to `NETStandard.Library` version `1.6.0`.</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="93c5f-135">Затем следует восстановить пакеты с помощью команды `dotnet restore` ([см. примечание](#dotnet-restore-note)), просмотреть файл `project.lock.json` и найти все пакеты, восстановленные для `NETSTandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-135">Next, you restore packages with `dotnet restore` ([see note](#dotnet-restore-note)), inspect the `project.lock.json` file, and find all the packages restored for `NETSTandard.Library`.</span></span>

<span data-ttu-id="93c5f-136">Вот как выглядит соответствующий раздел в файле `project.lock.json` при нацеливании на `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-136">Here's what the relevant section in the `project.lock.json` file looks like when targeting `netstandard1.0`:</span></span>

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

<span data-ttu-id="93c5f-137">Далее скопируйте ссылки на пакеты в раздел `dependencies` файла `project.json` библиотеки, заменив ссылку на `NETStandard.Library`:</span><span class="sxs-lookup"><span data-stu-id="93c5f-137">Next, copy over the package references into the `dependencies` section of the library's `project.json` file, replacing the `NETStandard.Library` reference:</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

<span data-ttu-id="93c5f-138">Получилось весьма много пакетов, многие из которых определенно не требуются для расширения типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="93c5f-138">That's quite a lot of packages, many of which which certainly aren't necessary for extending collection types.</span></span>  <span data-ttu-id="93c5f-139">Вы можете удалить пакеты вручную или использовать такое средство, как [ILSpy](http://ilspy.net) или [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector), для определения пакетов, которые действительно используются в коде.</span><span class="sxs-lookup"><span data-stu-id="93c5f-139">You can either remove packages manually or use a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to identify which packages your code actually uses.</span></span>

<span data-ttu-id="93c5f-140">Вот как может выглядеть усеченный пакет.</span><span class="sxs-lookup"><span data-stu-id="93c5f-140">Here's what a trimmed package could look like:</span></span>

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="93c5f-141">Теперь он имеет меньший размер, чем если бы он зависел от метапакета `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="93c5f-141">Now, it has a smaller footprint than if it had depended on the `NETStandard.Library` metapackage.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]