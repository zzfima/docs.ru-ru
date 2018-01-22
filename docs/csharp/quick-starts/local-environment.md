---
title: "Краткое руководство: использование C# в локальной среде"
description: "Это краткое руководство содержит основные сведения о выполнении кратких руководств в локальной среде."
author: billwagner
ms.topic: article
ms.date: 12/07/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: e7747941a7fb1ff43b1a259a78d82665b024a6dd
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2018
---
# <a name="local-environment"></a><span data-ttu-id="6109d-103">Локальная среда</span><span class="sxs-lookup"><span data-stu-id="6109d-103">Local environment</span></span>

<span data-ttu-id="6109d-104">Чтобы выполнить локально краткое руководство, сначала нужно настроить среду разработки на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6109d-104">The first step to trying a quick start locally is to setup a development environment on your local machine.</span></span>
<span data-ttu-id="6109d-105">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="6109d-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="6109d-106">Кроме того, вы можете установить [пакет SDK для .NET Core](http://dot.net/core) и [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="6109d-106">Alternatively, you can install the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="6109d-107">Основная последовательность разработки приложения</span><span class="sxs-lookup"><span data-stu-id="6109d-107">Basic application development flow</span></span>

<span data-ttu-id="6109d-108">Чтобы создать приложения, выполните команду [`dotnet new`](../../core/tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="6109d-108">You'll create applications using the [`dotnet new`](../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="6109d-109">Эта команда создает файлы и ресурсы, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="6109d-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="6109d-110">Во всех кратких приложениях используется тип приложения `console`.</span><span class="sxs-lookup"><span data-stu-id="6109d-110">The quickstarts all use the `console` application type.</span></span>

<span data-ttu-id="6109d-111">Выполните команду [`dotnet build`](../../core/tools/dotnet-build.md), чтобы создать исполняемый файл. Затем запустите исполняемый файла с помощью команды [`dotnet run`](../../core/tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="6109d-111">The other commands you'll use are [`dotnet build`](../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-quickstart"></a><span data-ttu-id="6109d-112">Выбор краткого руководства</span><span class="sxs-lookup"><span data-stu-id="6109d-112">Pick your quickstart</span></span>

<span data-ttu-id="6109d-113">Начните с любого из следующих кратких руководств:</span><span class="sxs-lookup"><span data-stu-id="6109d-113">You can start with any of the following quick starts:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="6109d-114">Числа в C#</span><span class="sxs-lookup"><span data-stu-id="6109d-114">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="6109d-115">В кратком руководстве [Числа в C#](numbers-in-csharp-local.md) вы узнаете, каким образом компьютер хранит числа и как выполнять вычисления с их различными типами.</span><span class="sxs-lookup"><span data-stu-id="6109d-115">In the [Numbers in C#](numbers-in-csharp-local.md) quick start, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="6109d-116">Вы ознакомитесь с основами округления и научитесь выполнять математические вычисления с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="6109d-116">You'll learn the basics of rounding, and how to perform mathematical calculations using C#.</span></span> 

<span data-ttu-id="6109d-117">В нем предполагается, что вы изучили руководство [Hello world](hello-world.yml).</span><span class="sxs-lookup"><span data-stu-id="6109d-117">This quick start assumes that you have finished the [Hello world](hello-world.yml) tutorial.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="6109d-118">Ветви и циклы</span><span class="sxs-lookup"><span data-stu-id="6109d-118">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="6109d-119">Краткое руководство [Ветви и циклы](branches-and-loops-local.md) покажет вам общие принципы выбора различных путей выполнения кода в зависимости от значений, хранящихся в переменных.</span><span class="sxs-lookup"><span data-stu-id="6109d-119">The [Branches and loops](branches-and-loops-local.md) quick start teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="6109d-120">Вы узнаете, что такое поток управления, являющийся основой принятия решений и выбора различных действий в программах.</span><span class="sxs-lookup"><span data-stu-id="6109d-120">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span> 

<span data-ttu-id="6109d-121">В этом занятии начального уровня предполагается, что вы изучили руководства [Hello World](hello-world.yml) и [Числа в C#](numbers-in-csharp-local.md).</span><span class="sxs-lookup"><span data-stu-id="6109d-121">This beginning lesson assumes that you have finished the [Hello World](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="6109d-122">Коллекция списков</span><span class="sxs-lookup"><span data-stu-id="6109d-122">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="6109d-123">Занятие [Коллекция списков](arrays-and-collections.md) содержит обзор типа "Коллекция списков", в котором хранятся последовательности данных.</span><span class="sxs-lookup"><span data-stu-id="6109d-123">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="6109d-124">Вы узнаете, как добавлять и удалять элементы, выполнять их поиск и сортировать списки.</span><span class="sxs-lookup"><span data-stu-id="6109d-124">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="6109d-125">Вы ознакомитесь с различными типами списков.</span><span class="sxs-lookup"><span data-stu-id="6109d-125">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="6109d-126">В этом кратком руководстве начального уровня предполагается, что вы изучили краткие руководства, перечисленные выше.</span><span class="sxs-lookup"><span data-stu-id="6109d-126">This beginning quick start assumes that you have finished the quick starts listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="6109d-127">Общие сведения о классах</span><span class="sxs-lookup"><span data-stu-id="6109d-127">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="6109d-128">Это заключительное краткое руководство выполняется только на компьютере с использованием локальной среды разработки и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6109d-128">This final quickstart is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="6109d-129">Вы создадите консольное приложение и изучите основные объектно-ориентированные функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="6109d-129">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
