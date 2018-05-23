---
title: Руководство по локальной среде. Краткие руководства по локальной разработке на C#
description: Это краткое руководство содержит основные сведения о выполнении кратких руководств в локальной среде.
ms.date: 12/07/2017
ms.custom: mvc
ms.openlocfilehash: ad8405bf9d453bd2cc5fad8af4b7897654368a9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="local-environment"></a><span data-ttu-id="02464-103">Локальная среда</span><span class="sxs-lookup"><span data-stu-id="02464-103">Local environment</span></span>

<span data-ttu-id="02464-104">Чтобы выполнить локально краткое руководство, сначала нужно настроить среду разработки на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="02464-104">The first step to trying a quickstart locally is to setup a development environment on your local machine.</span></span>
<span data-ttu-id="02464-105">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="02464-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="02464-106">Кроме того, вы можете установить [пакет SDK для .NET Core](http://dot.net/core) и [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="02464-106">Alternatively, you can install the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="02464-107">Основная последовательность разработки приложения</span><span class="sxs-lookup"><span data-stu-id="02464-107">Basic application development flow</span></span>

<span data-ttu-id="02464-108">Чтобы создать приложения, выполните команду [`dotnet new`](../../core/tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="02464-108">You'll create applications using the [`dotnet new`](../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="02464-109">Эта команда создает файлы и ресурсы, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="02464-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="02464-110">Во всех кратких приложениях используется тип приложения `console`.</span><span class="sxs-lookup"><span data-stu-id="02464-110">The quickstarts all use the `console` application type.</span></span>

<span data-ttu-id="02464-111">Выполните команду [`dotnet build`](../../core/tools/dotnet-build.md), чтобы создать исполняемый файл. Затем запустите исполняемый файла с помощью команды [`dotnet run`](../../core/tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="02464-111">The other commands you'll use are [`dotnet build`](../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-quickstart"></a><span data-ttu-id="02464-112">Выбор краткого руководства</span><span class="sxs-lookup"><span data-stu-id="02464-112">Pick your quickstart</span></span>

<span data-ttu-id="02464-113">Начните с любого из следующих кратких руководств.</span><span class="sxs-lookup"><span data-stu-id="02464-113">You can start with any of the following quickstarts:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="02464-114">Числа в C#</span><span class="sxs-lookup"><span data-stu-id="02464-114">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="02464-115">В кратком руководстве [Числа в C#](numbers-in-csharp-local.md) вы узнаете, каким образом на компьютере хранятся числа и как выполнять вычисления с разными числовыми типами.</span><span class="sxs-lookup"><span data-stu-id="02464-115">In the [Numbers in C#](numbers-in-csharp-local.md) quickstart, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="02464-116">Вы ознакомитесь с основами округления и научитесь выполнять математические вычисления с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="02464-116">You'll learn the basics of rounding, and how to perform mathematical calculations using C#.</span></span> 

<span data-ttu-id="02464-117">Это руководство предполагает, что вы выполнили урок [Hello World](hello-world.yml).</span><span class="sxs-lookup"><span data-stu-id="02464-117">This quickstart assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="02464-118">Ветви и циклы</span><span class="sxs-lookup"><span data-stu-id="02464-118">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="02464-119">В кратком руководстве [Ветви и циклы](branches-and-loops-local.md) представлены общие принципы организации ветвления кода в зависимости от значений, хранящихся в переменных.</span><span class="sxs-lookup"><span data-stu-id="02464-119">The [Branches and loops](branches-and-loops-local.md) quickstart teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="02464-120">Вы узнаете, что такое поток управления, являющийся основой принятия решений и выбора различных действий в программах.</span><span class="sxs-lookup"><span data-stu-id="02464-120">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span> 

<span data-ttu-id="02464-121">Это руководство предполагает, что вы выполнили уроки [Hello World](hello-world.yml) и [Числа в C#](numbers-in-csharp-local.md).</span><span class="sxs-lookup"><span data-stu-id="02464-121">This quickstart assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="string-interpolationinterpolated-strings-localmd"></a>[<span data-ttu-id="02464-122">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="02464-122">String interpolation</span></span>](interpolated-strings-local.md)

<span data-ttu-id="02464-123">Краткое руководство [Интерполяция строк](interpolated-strings-local.md) покажет вам, как вставлять значения в строку.</span><span class="sxs-lookup"><span data-stu-id="02464-123">The [String interpolation](interpolated-strings-local.md) quickstart shows you how to insert values into a string.</span></span> <span data-ttu-id="02464-124">Вы узнаете, как создать интерполированную строку с внедренными выражениями C# и как управлять текстовым представлением результатов выражений в итоговой строке.</span><span class="sxs-lookup"><span data-stu-id="02464-124">You'll learn how to create an interpolated string with embedded C# expressions and how to control the text appearance of the expression results in the result string.</span></span>

<span data-ttu-id="02464-125">Это руководство предполагает, что вы прошли уроки [Hello World](hello-world.yml), [Числа в C#](numbers-in-csharp-local.md), а также [Ветви и циклы](branches-and-loops-local.md).</span><span class="sxs-lookup"><span data-stu-id="02464-125">This quickstart assumes that you have finished the [Hello world](hello-world.yml), [Numbers in C#](numbers-in-csharp-local.md), and [Branches and loops](branches-and-loops-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="02464-126">Коллекция списков</span><span class="sxs-lookup"><span data-stu-id="02464-126">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="02464-127">Занятие [Коллекция списков](arrays-and-collections.md) содержит обзор типа "Коллекция списков", в котором хранятся последовательности данных.</span><span class="sxs-lookup"><span data-stu-id="02464-127">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="02464-128">Вы узнаете, как добавлять и удалять элементы, выполнять их поиск и сортировать списки.</span><span class="sxs-lookup"><span data-stu-id="02464-128">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="02464-129">Вы ознакомитесь с различными типами списков.</span><span class="sxs-lookup"><span data-stu-id="02464-129">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="02464-130">Это руководство предполагает, что вы прошли уроки, перечисленные выше.</span><span class="sxs-lookup"><span data-stu-id="02464-130">This quickstart assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="02464-131">Общие сведения о классах</span><span class="sxs-lookup"><span data-stu-id="02464-131">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="02464-132">Это заключительное краткое руководство доступно для запуска только в локальной среде разработки с .NET Core на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="02464-132">This final quickstart is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="02464-133">Вы создадите консольное приложение и изучите основные объектно-ориентированные функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="02464-133">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
