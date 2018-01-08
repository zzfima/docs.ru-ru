---
title: "Перенос кода в .NET Core — анализ зависимостей сторонних разработчиков"
description: "Перенос кода в .NET Core — анализ зависимостей сторонних разработчиков"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.workload: dotnetcore
ms.openlocfilehash: 70b39c9762e4ee7450d0f59455bace0ac728844c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="porting-to-net-core---analyzing-your-third-party-party-dependencies"></a><span data-ttu-id="3bf88-104">Перенос кода в .NET Core — анализ зависимостей сторонних разработчиков</span><span class="sxs-lookup"><span data-stu-id="3bf88-104">Porting to .NET Core - Analyzing your Third-Party Party Dependencies</span></span>

<span data-ttu-id="3bf88-105">Первый этап процесса переноса — анализ зависимостей сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="3bf88-105">The first step in the porting process is to understand your third party dependencies.</span></span>  <span data-ttu-id="3bf88-106">Необходимо выяснить, есть ли среди них такие, которые не выполняются в .NET Core, и разработать для них план на непредвиденные случаи.</span><span class="sxs-lookup"><span data-stu-id="3bf88-106">You need to figure out which of them, if any, don't yet run on .NET Core, and develop a contingency plan for those which don't run on .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3bf88-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3bf88-107">Prerequisites</span></span>

<span data-ttu-id="3bf88-108">В этой статье предполагается, что вы используете Windows и Visual Studio и что у вас есть код, который в настоящее время выполняется в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3bf88-108">This article will assume you are using Windows and Visual Studio, and that you have code which runs on the .NET Framework today.</span></span>

## <a name="analyzing-nuget-packages"></a><span data-ttu-id="3bf88-109">Анализ пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="3bf88-109">Analyzing NuGet Packages</span></span>

<span data-ttu-id="3bf88-110">Проанализировать переносимость пакетов NuGet легко.</span><span class="sxs-lookup"><span data-stu-id="3bf88-110">Analyzing NuGet packages for portability is very easy.</span></span>  <span data-ttu-id="3bf88-111">Так как пакет NuGet представляет собой набор папок, которые содержат сборки для конкретных платформ, вам нужно всего лишь проверить, есть ли папка, содержащая сборку .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3bf88-111">Because a NuGet package is itself a set of folders which contain platform-specific assemblies, all you have to do is check to see if there is a folder which contains a .NET Core assembly.</span></span>

<span data-ttu-id="3bf88-112">Просматривать папки пакета NuGet проще всего с помощью средства [Обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="3bf88-112">Inspecting NuGet Package folders is easiest with the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span>  <span data-ttu-id="3bf88-113">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="3bf88-113">Here's how to do it.</span></span>

1. <span data-ttu-id="3bf88-114">Скачайте и откройте обозреватель пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="3bf88-114">Download and open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="3bf88-115">Щелкните "Открыть пакет из веб-канала".</span><span class="sxs-lookup"><span data-stu-id="3bf88-115">Click "Open package from online feed".</span></span>
3. <span data-ttu-id="3bf88-116">Выполните поиск по имени пакета.</span><span class="sxs-lookup"><span data-stu-id="3bf88-116">Search for the name of the package.</span></span>
4. <span data-ttu-id="3bf88-117">Разверните папку lib в правой части окна и просмотрите имена папок.</span><span class="sxs-lookup"><span data-stu-id="3bf88-117">Expand the "lib" folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="3bf88-118">Поддерживаемые пакетом платформы можно также просмотреть на сайте [nuget.org](https://www.nuget.org/) в разделе **Dependencies** на странице этого пакета.</span><span class="sxs-lookup"><span data-stu-id="3bf88-118">You can also see what a package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the page for that package.</span></span>

<span data-ttu-id="3bf88-119">В любом случае вам нужно найти папку или запись на сайте [nuget.org](https://www.nuget.org/) с любым из следующих имен:</span><span class="sxs-lookup"><span data-stu-id="3bf88-119">In either case, you'll need to look for a folder or entry on [nuget.org](https://www.nuget.org/) with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="3bf88-120">Это моникеры целевых платформ (TFM), которые соответствуют версиям [.NET Standard](../../standard/net-standard.md) и традиционным профилям переносимой библиотеки классов (PCL), совместимым с .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3bf88-120">These are the Target Framework Monikers (TFM) which map to versions of the [.NET Standard](../../standard/net-standard.md) and traditional Portable Class Library (PCL) profiles which are compatible with .NET Core.</span></span>  <span data-ttu-id="3bf88-121">Имейте в виду, что, хотя платформа `netcoreapp1.0` совместима, она предназначена для приложений, а не библиотек.</span><span class="sxs-lookup"><span data-stu-id="3bf88-121">Note that `netcoreapp1.0`, while compatible, is for applications and not libraries.</span></span>  <span data-ttu-id="3bf88-122">Хотя вы вполне можете использовать библиотеку на основе `netcoreapp1.0`, она будет предназначена *только* для использования другими приложениями `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="3bf88-122">Although there's nothing wrong with using a library which is `netcoreapp1.0`-based, that library may not be intended for anything *other* than consumption by other `netcoreapp1.0` applications.</span></span>

<span data-ttu-id="3bf88-123">Есть также ряд устаревших моникеров TFM из предварительных версий .NET Core, которые также могут быть совместимыми:</span><span class="sxs-lookup"><span data-stu-id="3bf88-123">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="3bf88-124">**Хотя они, скорее всего, будут работать с кодом, гарантии совместимости нет**.</span><span class="sxs-lookup"><span data-stu-id="3bf88-124">**While these will likely work with your code, there is no guarantee of compatibility**.</span></span>  <span data-ttu-id="3bf88-125">Пакеты с этими моникерами TFM были созданы с использованием предварительных версий пакетов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3bf88-125">Packages with these TFMs were built with pre-release .NET Core packages.</span></span>  <span data-ttu-id="3bf88-126">Обратите внимание на то, когда подобные пакеты будут обновлены до версии `netstandard` (если будут ли вообще).</span><span class="sxs-lookup"><span data-stu-id="3bf88-126">Take note of when (or if) packages like this are updated to be `netstandard`-based.</span></span>

> [!NOTE]
> <span data-ttu-id="3bf88-127">Чтобы использовать пакет, предназначенный для традиционной библиотеки PCL или предварительной версии .NET Core, необходимо использовать директиву `imports` в файле `project.json`.</span><span class="sxs-lookup"><span data-stu-id="3bf88-127">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `imports` directive in your `project.json` file.</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="3bf88-128">Что делать, если зависимость пакета NuGet не работает в .NET Core</span><span class="sxs-lookup"><span data-stu-id="3bf88-128">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="3bf88-129">Если пакет NuGet, от которого зависит ваш проект, не работает в .NET Core, можно предпринять ряд мер.</span><span class="sxs-lookup"><span data-stu-id="3bf88-129">There are a few things you can do if a NuGet package you depend on won't run on .NET Core.</span></span>

1. <span data-ttu-id="3bf88-130">Если проект имеет открытый исходный код и размещается на каком либо ресурсе, наподобие GitHub, вы можете обратиться к разработчикам напрямую.</span><span class="sxs-lookup"><span data-stu-id="3bf88-130">If the project is open source and hosted somewhere like GitHub, you can engage the developer(s) directly.</span></span>
2. <span data-ttu-id="3bf88-131">Вы можете связаться с автором непосредственно на сайте [nuget.org](https://www.nuget.org/), найдя пакет и щелкнув "Связаться с владельцами" в левой части его страницы.</span><span class="sxs-lookup"><span data-stu-id="3bf88-131">You can contact the author directly on [nuget.org](https://www.nuget.org/) by searching for the package and clicking "Contact Owners" on the left hand side of the package's page.</span></span>
3. <span data-ttu-id="3bf88-132">Вы можете поискать другой пакет, работающий в .NET Core и выполняющий ту же задачу, что и используемый вами пакет.</span><span class="sxs-lookup"><span data-stu-id="3bf88-132">You can look for another package that runs on .NET Core which accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="3bf88-133">Вы можете попытаться создать пакет с аналогичным кодом самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="3bf88-133">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="3bf88-134">Вы можете устранить зависимость от пакета, изменив функциональность приложения, по крайней мере до тех пор пока не станет доступна совместимая версия пакета.</span><span class="sxs-lookup"><span data-stu-id="3bf88-134">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="3bf88-135">Помните, что участники проектов с открытым исходным кодом и издатели пакетов NuGet зачастую являются добровольцами, которые тратят свои усилия, потому что им интересна эта область деятельности, делают это бесплатно и часто имеют другую постоянную работу.</span><span class="sxs-lookup"><span data-stu-id="3bf88-135">Please remember that open source project maintainers and NuGet package publishers are often volunteers who contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="3bf88-136">Начиная общение с ними, вы можете сделать одобрительное замечание о библиотеке, прежде чем просить о поддержке платформы .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3bf88-136">If you do reach out, you might start with a positive statement about the library before asking about .NET Core support.</span></span>

<span data-ttu-id="3bf88-137">Если ни один из описанных выше способов не помог решить проблему, возможно, придется отложить перенос кода в .NET Core на более позднюю дату.</span><span class="sxs-lookup"><span data-stu-id="3bf88-137">If you're unable to resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="3bf88-138">Команда разработчиков .NET хотела бы узнать, поддержку каких библиотек в .NET Core следует реализовать в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="3bf88-138">The .NET Team would like to know which libraries are the most important to support next with .NET Core.</span></span> <span data-ttu-id="3bf88-139">Вы можете написать нам на адрес dotnet@microsoft.com, чтобы сообщить о библиотеках, которые хотели бы использовать.</span><span class="sxs-lookup"><span data-stu-id="3bf88-139">You can also send us mail at dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a><span data-ttu-id="3bf88-140">Анализ зависимостей, которые не являются пакетами NuGet</span><span class="sxs-lookup"><span data-stu-id="3bf88-140">Analyzing Dependencies which aren't NuGet Packages</span></span>

<span data-ttu-id="3bf88-141">У вас может быть зависимость, которая не является пакетом NuGet, например библиотека DLL в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="3bf88-141">You may have a dependency that isn't a NuGet package, such as a DLL in the filesystem.</span></span>  <span data-ttu-id="3bf88-142">Единственный способ определить переносимость такой зависимости — запустить [средство ApiPort](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span><span class="sxs-lookup"><span data-stu-id="3bf88-142">The only way to determine the portability of that dependency is to run the [ApiPort tool](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3bf88-143">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="3bf88-143">Next steps</span></span>

<span data-ttu-id="3bf88-144">Если вы переносите библиотеку, обратитесь к разделу о [переносе библиотек](libraries.md).</span><span class="sxs-lookup"><span data-stu-id="3bf88-144">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
