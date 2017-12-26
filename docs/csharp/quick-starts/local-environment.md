---
title: "Краткое руководство: использование C# в локальной среде"
description: "Это краткое руководство содержит основные сведения о выполнении кратких руководств в локальной среде."
author: billwagner
ms.author: wiwagn
ms.date: 12/07/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4cbe66df4173854870dd6ac68c52e8c87c46c1f6
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2017
---
# <a name="local-environment"></a><span data-ttu-id="a0a79-103">Локальная среда</span><span class="sxs-lookup"><span data-stu-id="a0a79-103">Local environment</span></span>

<span data-ttu-id="a0a79-104">Чтобы выполнить локально краткое руководство, сначала нужно настроить среду разработки на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0a79-104">The first step to trying a quick start locally is to setup a development environment on your local machine.</span></span>
<span data-ttu-id="a0a79-105">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="a0a79-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="a0a79-106">Кроме того, вы можете установить [пакет SDK для .NET Core](http://dot.net/core) и [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="a0a79-106">Alternatively, you can install the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="a0a79-107">Основная последовательность разработки приложения</span><span class="sxs-lookup"><span data-stu-id="a0a79-107">Basic application development flow</span></span>

<span data-ttu-id="a0a79-108">Чтобы создать приложения, выполните команду [`dotnet new`](../../core/tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="a0a79-108">You'll create applications using the [`dotnet new`](../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="a0a79-109">Эта команда создает файлы и ресурсы, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="a0a79-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="a0a79-110">Во всех кратких приложениях используется тип приложения `console`.</span><span class="sxs-lookup"><span data-stu-id="a0a79-110">The quickstarts all use the `console` application type.</span></span>

<span data-ttu-id="a0a79-111">Выполните команду [`dotnet build`](../../core/tools/dotnet-build.md), чтобы создать исполняемый файл. Затем запустите исполняемый файла с помощью команды [`dotnet run`](../../core/tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="a0a79-111">The other commands you'll use are [`dotnet build`](../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-quickstart"></a><span data-ttu-id="a0a79-112">Выбор краткого руководства</span><span class="sxs-lookup"><span data-stu-id="a0a79-112">Pick your quickstart</span></span>

<span data-ttu-id="a0a79-113">Начните с любого из следующих кратких руководств:</span><span class="sxs-lookup"><span data-stu-id="a0a79-113">You can start with any of the following quick starts:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="a0a79-114">Числа в C#</span><span class="sxs-lookup"><span data-stu-id="a0a79-114">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="a0a79-115">В кратком руководстве [Числа в C#](numbers-in-csharp-local.md) вы узнаете, каким образом компьютер хранит числа и как выполнять вычисления с их различными типами.</span><span class="sxs-lookup"><span data-stu-id="a0a79-115">In the [Numbers in C#](numbers-in-csharp-local.md) quick start, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="a0a79-116">Вы ознакомитесь с основами округления и научитесь выполнять математические вычисления с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="a0a79-116">You'll learn the basics of rounding, and how to perform mathematical calculations using C#.</span></span> 

<span data-ttu-id="a0a79-117">В нем предполагается, что вы изучили руководство [Hello world](hello-world.yml).</span><span class="sxs-lookup"><span data-stu-id="a0a79-117">This quick start assumes that you have finished the [Hello world](hello-world.yml) tutorial.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="a0a79-118">Ветви и циклы</span><span class="sxs-lookup"><span data-stu-id="a0a79-118">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="a0a79-119">Краткое руководство [Ветви и циклы](branches-and-loops-local.md) покажет вам общие принципы выбора различных путей выполнения кода в зависимости от значений, хранящихся в переменных.</span><span class="sxs-lookup"><span data-stu-id="a0a79-119">The [Branches and loops](branches-and-loops-local.md) quick start teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="a0a79-120">Вы узнаете, что такое поток управления, являющийся основой принятия решений и выбора различных действий в программах.</span><span class="sxs-lookup"><span data-stu-id="a0a79-120">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span> 

<span data-ttu-id="a0a79-121">В этом занятии начального уровня предполагается, что вы изучили руководства [Hello World](hello-world.yml) и [Числа в C#](numbers-in-csharp-local.md).</span><span class="sxs-lookup"><span data-stu-id="a0a79-121">This beginning lesson assumes that you have finished the [Hello World](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="a0a79-122">Коллекция списков</span><span class="sxs-lookup"><span data-stu-id="a0a79-122">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="a0a79-123">Занятие [Коллекция списков](arrays-and-collections.md) содержит обзор типа "Коллекция списков", в котором хранятся последовательности данных.</span><span class="sxs-lookup"><span data-stu-id="a0a79-123">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="a0a79-124">Вы узнаете, как добавлять и удалять элементы, выполнять их поиск и сортировать списки.</span><span class="sxs-lookup"><span data-stu-id="a0a79-124">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="a0a79-125">Вы ознакомитесь с различными типами списков.</span><span class="sxs-lookup"><span data-stu-id="a0a79-125">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="a0a79-126">В этом кратком руководстве начального уровня предполагается, что вы изучили краткие руководства, перечисленные выше.</span><span class="sxs-lookup"><span data-stu-id="a0a79-126">This beginning quick start assumes that you have finished the quick starts listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="a0a79-127">Общие сведения о классах</span><span class="sxs-lookup"><span data-stu-id="a0a79-127">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="a0a79-128">Это заключительное краткое руководство выполняется только на компьютере с использованием локальной среды разработки и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a0a79-128">This final quickstart is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="a0a79-129">Вы создадите консольное приложение и изучите основные объектно-ориентированные функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="a0a79-129">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
