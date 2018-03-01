---
title: "Руководство по локальной среде. Краткие руководства по локальной разработке на C#"
description: "Это краткое руководство содержит основные сведения о выполнении кратких руководств в локальной среде."
author: billwagner
ms.topic: article
ms.date: 12/07/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 9957f524e04f8ff64d4f640cf085b16cf9a2c0c6
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="local-environment"></a><span data-ttu-id="5e3c6-103">Локальная среда</span><span class="sxs-lookup"><span data-stu-id="5e3c6-103">Local environment</span></span>

<span data-ttu-id="5e3c6-104">Чтобы выполнить локально краткое руководство, сначала нужно настроить среду разработки на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-104">The first step to trying a quickstart locally is to setup a development environment on your local machine.</span></span>
<span data-ttu-id="5e3c6-105">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="5e3c6-106">Кроме того, вы можете установить [пакет SDK для .NET Core](http://dot.net/core) и [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="5e3c6-106">Alternatively, you can install the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="5e3c6-107">Основная последовательность разработки приложения</span><span class="sxs-lookup"><span data-stu-id="5e3c6-107">Basic application development flow</span></span>

<span data-ttu-id="5e3c6-108">Чтобы создать приложения, выполните команду [`dotnet new`](../../core/tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="5e3c6-108">You'll create applications using the [`dotnet new`](../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="5e3c6-109">Эта команда создает файлы и ресурсы, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="5e3c6-110">Во всех кратких приложениях используется тип приложения `console`.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-110">The quickstarts all use the `console` application type.</span></span>

<span data-ttu-id="5e3c6-111">Выполните команду [`dotnet build`](../../core/tools/dotnet-build.md), чтобы создать исполняемый файл. Затем запустите исполняемый файла с помощью команды [`dotnet run`](../../core/tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="5e3c6-111">The other commands you'll use are [`dotnet build`](../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-quickstart"></a><span data-ttu-id="5e3c6-112">Выбор краткого руководства</span><span class="sxs-lookup"><span data-stu-id="5e3c6-112">Pick your quickstart</span></span>

<span data-ttu-id="5e3c6-113">Начните с любого из следующих кратких руководств.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-113">You can start with any of the following quickstarts:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="5e3c6-114">Числа в C#</span><span class="sxs-lookup"><span data-stu-id="5e3c6-114">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="5e3c6-115">В кратком руководстве [по числам в C#](numbers-in-csharp-local.md) вы узнаете, каким образом на компьютере хранятся числа и как выполнять вычисления с их разными типами.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-115">In the [Numbers in C#](numbers-in-csharp-local.md) quickstart, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="5e3c6-116">Вы ознакомитесь с основами округления и научитесь выполнять математические вычисления с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-116">You'll learn the basics of rounding, and how to perform mathematical calculations using C#.</span></span> 

<span data-ttu-id="5e3c6-117">В руководстве предполагается, что вы изучили руководство [Hello World](hello-world.yml).</span><span class="sxs-lookup"><span data-stu-id="5e3c6-117">This quickstart assumes that you have finished the [Hello world](hello-world.yml) tutorial.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="5e3c6-118">Ветви и циклы</span><span class="sxs-lookup"><span data-stu-id="5e3c6-118">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="5e3c6-119">В кратком руководстве [Ветви и циклы](branches-and-loops-local.md) представлены общие принципы организации ветвления кода в зависимости от значений, хранящихся в переменных.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-119">The [Branches and loops](branches-and-loops-local.md) quickstart teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="5e3c6-120">Вы узнаете, что такое поток управления, являющийся основой принятия решений и выбора различных действий в программах.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-120">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span> 

<span data-ttu-id="5e3c6-121">В этом занятии начального уровня предполагается, что вы изучили руководства [Hello World](hello-world.yml) и [Числа в C#](numbers-in-csharp-local.md).</span><span class="sxs-lookup"><span data-stu-id="5e3c6-121">This beginning lesson assumes that you have finished the [Hello World](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="5e3c6-122">Коллекция списков</span><span class="sxs-lookup"><span data-stu-id="5e3c6-122">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="5e3c6-123">Занятие [Коллекция списков](arrays-and-collections.md) содержит обзор типа "Коллекция списков", в котором хранятся последовательности данных.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-123">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="5e3c6-124">Вы узнаете, как добавлять и удалять элементы, выполнять их поиск и сортировать списки.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-124">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="5e3c6-125">Вы ознакомитесь с различными типами списков.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-125">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="5e3c6-126">В этом кратком руководстве начального уровня предполагается, что вы изучили краткие руководства, перечисленные выше.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-126">This beginning quickstart assumes that you have finished the quickstarts listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="5e3c6-127">Общие сведения о классах</span><span class="sxs-lookup"><span data-stu-id="5e3c6-127">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="5e3c6-128">Это заключительное краткое руководство выполняется только на компьютере с использованием локальной среды разработки и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-128">This final quickstart is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="5e3c6-129">Вы создадите консольное приложение и изучите основные объектно-ориентированные функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="5e3c6-129">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
