---
title: Сокращение зависимостей пакетов с помощью файла project.json
description: Сократите зависимости пакетов при создании библиотек на базе project.json.
author: cartermp
ms.date: 06/20/2016
ms.openlocfilehash: 48ba3ef578388fd98fe7cb830df313512d359483
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740823"
---
# <a name="reducing-package-dependencies-with-projectjson"></a><span data-ttu-id="2b842-103">Сокращение зависимостей пакетов с помощью файла project.json</span><span class="sxs-lookup"><span data-stu-id="2b842-103">Reducing Package Dependencies with project.json</span></span>

<span data-ttu-id="2b842-104">В этой статье приводятся необходимые сведения о сокращении зависимостей пакетов при разработке библиотек `project.json`.</span><span class="sxs-lookup"><span data-stu-id="2b842-104">This article covers what you need to know about reducing your package dependencies when authoring `project.json` libraries.</span></span> <span data-ttu-id="2b842-105">К концу этой статьи вы научитесь составлять библиотеки так, чтобы в них использовались только необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="2b842-105">By the end of this article, you will learn how to compose your library such that it only uses the dependencies it needs.</span></span>

## <a name="why-its-important"></a><span data-ttu-id="2b842-106">Почему это важно</span><span class="sxs-lookup"><span data-stu-id="2b842-106">Why it's Important</span></span>

<span data-ttu-id="2b842-107">.NET Core — это продукт, состоящий из пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="2b842-107">.NET Core is a product made up of NuGet packages.</span></span>  <span data-ttu-id="2b842-108">Базовый пакет — это [метапакет NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library). Он представляет собой пакет NuGet, состоящий из других пакетов.</span><span class="sxs-lookup"><span data-stu-id="2b842-108">An essential package is the [.NETStandard.Library metapackage](https://www.nuget.org/packages/NETStandard.Library), which is a NuGet package composed of other packages.</span></span> <span data-ttu-id="2b842-109">Этот метапакет предоставляет набор пакетов, которые гарантированно работают в разных реализациях .NET, таких как .NET Framework, .NET Core и Xamarin/Mono.</span><span class="sxs-lookup"><span data-stu-id="2b842-109">It provides you with the set of packages that are guaranteed to work on multiple .NET implementations, such as .NET Framework, .NET Core, and Xamarin/Mono.</span></span>

<span data-ttu-id="2b842-110">Однако высока вероятность того, что ваша библиотека будет использовать не все входящие в него пакеты.</span><span class="sxs-lookup"><span data-stu-id="2b842-110">However, there's a good chance that your library won't use every single package it contains.</span></span>  <span data-ttu-id="2b842-111">При разработке библиотеки и ее распространении посредством NuGet рекомендуется "усекать" зависимости, оставляя только действительно необходимые.</span><span class="sxs-lookup"><span data-stu-id="2b842-111">When authoring a library and distributing it over NuGet, it's a best practice to "trim" your dependencies down to only the packages you actually use.</span></span>  <span data-ttu-id="2b842-112">Результатом является уменьшение общего размера пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="2b842-112">This results in a smaller overall footprint for NuGet packages.</span></span>

## <a name="how-to-do-it"></a><span data-ttu-id="2b842-113">Как это сделать</span><span class="sxs-lookup"><span data-stu-id="2b842-113">How to do it</span></span>

<span data-ttu-id="2b842-114">Сейчас нет официальной команды `dotnet`, которая усекает ссылки на пакеты.</span><span class="sxs-lookup"><span data-stu-id="2b842-114">Currently, there is no official `dotnet` command that trims package references.</span></span>  <span data-ttu-id="2b842-115">Вам потребуется сделать это вручную.</span><span class="sxs-lookup"><span data-stu-id="2b842-115">Instead, you'll have to do it manually.</span></span>  <span data-ttu-id="2b842-116">Ниже описывается общая процедура:</span><span class="sxs-lookup"><span data-stu-id="2b842-116">The general process looks like the following:</span></span>

1. <span data-ttu-id="2b842-117">Укажите ссылку на `NETStandard.Library` версии `1.6.0` в разделе `dependencies` файла `project.json`.</span><span class="sxs-lookup"><span data-stu-id="2b842-117">Reference `NETStandard.Library` version `1.6.0` in a `dependencies` section of your `project.json`.</span></span>
2. <span data-ttu-id="2b842-118">Восстановите пакеты, выполнив команду `dotnet restore` ([см. примечание](#dotnet-restore-note)) в командной строке.</span><span class="sxs-lookup"><span data-stu-id="2b842-118">Restore packages with `dotnet restore` ([see note](#dotnet-restore-note)) from the command line.</span></span>
3. <span data-ttu-id="2b842-119">Просмотрите файл `project.lock.json` и найдите раздел `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="2b842-119">Inspect the `project.lock.json` file and find the `NETStandard.Library` section.</span></span>  <span data-ttu-id="2b842-120">Он находится ближе к началу файла.</span><span class="sxs-lookup"><span data-stu-id="2b842-120">It's near the beginning of the file.</span></span>
4. <span data-ttu-id="2b842-121">Скопируйте все пакеты, перечисленные в разделе `dependencies`.</span><span class="sxs-lookup"><span data-stu-id="2b842-121">Copy all of the listed packages under `dependencies`.</span></span>
5. <span data-ttu-id="2b842-122">Удалите ссылку на `.NETStandard.Library` и замените ее скопированными пакетами.</span><span class="sxs-lookup"><span data-stu-id="2b842-122">Remove the `.NETStandard.Library` reference and replace it with the copied packages.</span></span>
6. <span data-ttu-id="2b842-123">Удалите ссылки на пакеты, которые вам не нужны.</span><span class="sxs-lookup"><span data-stu-id="2b842-123">Remove references to packages you don't need.</span></span>

<span data-ttu-id="2b842-124">Узнать, какие пакеты вам не нужны, можно одним из указанных ниже способов:</span><span class="sxs-lookup"><span data-stu-id="2b842-124">You can find out which packages you don't need by one of the following ways:</span></span>

1. <span data-ttu-id="2b842-125">Методом проб и ошибок.</span><span class="sxs-lookup"><span data-stu-id="2b842-125">Trial and error.</span></span> <span data-ttu-id="2b842-126">То есть вам нужно удалить пакет, выполнить восстановление, проверить, компилируется ли по-прежнему библиотека, а затем повторить этот процесс.</span><span class="sxs-lookup"><span data-stu-id="2b842-126">This involves removing a package, restoring, seeing if your library still compiles, and repeating this process.</span></span>
2. <span data-ttu-id="2b842-127">С помощью такого средства, как [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) или [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector), изучить ссылки, чтобы узнать, какие из них действительно используются в коде.</span><span class="sxs-lookup"><span data-stu-id="2b842-127">Using a tool such as [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) or [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector) to peek at references to see what your code is actually using.</span></span> <span data-ttu-id="2b842-128">Затем можно удалить пакеты, которые не соответствуют используемым типам.</span><span class="sxs-lookup"><span data-stu-id="2b842-128">You can then remove packages that don't correspond to types you're using.</span></span>

## <a name="example"></a><span data-ttu-id="2b842-129">Пример</span><span class="sxs-lookup"><span data-stu-id="2b842-129">Example</span></span>

<span data-ttu-id="2b842-130">Представьте, что вы написали библиотеку, расширяющую функциональность универсальных типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="2b842-130">Imagine that you wrote a library that provided additional functionality to generic collection types.</span></span> <span data-ttu-id="2b842-131">Подобная библиотека обязательно будет зависеть от таких пакетов, как `System.Collections`, но может совершенно не использовать такие пакеты, как `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="2b842-131">Such a library would need to depend on packages such as `System.Collections`, but may not at all depend on packages such as `System.Net.Http`.</span></span> <span data-ttu-id="2b842-132">Поэтому было бы неплохо ограничить зависимости пакетов только теми, которые действительно требуются библиотеке.</span><span class="sxs-lookup"><span data-stu-id="2b842-132">As such, it would be good to trim package dependencies down to only what this library required!</span></span>

<span data-ttu-id="2b842-133">Чтобы усечь зависимости в этой библиотеке, необходимо начать с файла `project.json` и добавить ссылку на `NETStandard.Library` версии `1.6.0`.</span><span class="sxs-lookup"><span data-stu-id="2b842-133">To trim this library, you start with the `project.json` file and add a reference to `NETStandard.Library` version `1.6.0`.</span></span>

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

<span data-ttu-id="2b842-134">Затем следует восстановить пакеты с помощью команды `dotnet restore` ([см. примечание](#dotnet-restore-note)), просмотреть файл `project.lock.json` и найти все пакеты, восстановленные для `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="2b842-134">Next, you restore packages with `dotnet restore` ([see note](#dotnet-restore-note)), inspect the `project.lock.json` file, and find all the packages restored for `NETStandard.Library`.</span></span>

<span data-ttu-id="2b842-135">Вот как выглядит соответствующий раздел в файле `project.lock.json` при нацеливании на `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="2b842-135">Here's what the relevant section in the `project.lock.json` file looks like when targeting `netstandard1.0`:</span></span>

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

<span data-ttu-id="2b842-136">Далее скопируйте ссылки на пакеты в раздел `dependencies` файла `project.json` библиотеки, заменив ссылку на `NETStandard.Library`:</span><span class="sxs-lookup"><span data-stu-id="2b842-136">Next, copy over the package references into the `dependencies` section of the library's `project.json` file, replacing the `NETStandard.Library` reference:</span></span>

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

<span data-ttu-id="2b842-137">Получилось весьма много пакетов, многие из которых определенно не требуются для расширения типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="2b842-137">That's quite a lot of packages, many of which certainly aren't necessary for extending collection types.</span></span>  <span data-ttu-id="2b842-138">Вы можете удалить пакеты вручную или использовать такое средство, как [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) или [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/), для определения пакетов, которые действительно используются в коде.</span><span class="sxs-lookup"><span data-stu-id="2b842-138">You can either remove packages manually or use a tool such as [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) or [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/) to identify which packages your code actually uses.</span></span>

<span data-ttu-id="2b842-139">Вот как может выглядеть усеченный пакет.</span><span class="sxs-lookup"><span data-stu-id="2b842-139">Here's what a trimmed package could look like:</span></span>

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

<span data-ttu-id="2b842-140">Теперь он имеет меньший размер, чем если бы он зависел от метапакета `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="2b842-140">Now, it has a smaller footprint than if it had depended on the `NETStandard.Library` metapackage.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
