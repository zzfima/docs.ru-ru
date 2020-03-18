---
title: Знакомство со средствами разработки. Вводное руководство по C#
description: Эта статья содержит базовое описание средств разработки, которые вы будете использовать для создания приложений C# и .NET на локальном компьютере.
ms.date: 10/23/2018
ms.openlocfilehash: 0b1df9e733eef92b1eeb0a7f3ba3ba49602f219d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156575"
---
# <a name="become-familiar-with-the-net-development-tools"></a><span data-ttu-id="f4a38-103">Знакомство со средствами разработки для .NET</span><span class="sxs-lookup"><span data-stu-id="f4a38-103">Become familiar with the .NET development tools</span></span>

<span data-ttu-id="f4a38-104">Для выполнения этого руководства прежде всего нужно настроить на компьютере среду разработки.</span><span class="sxs-lookup"><span data-stu-id="f4a38-104">The first step in running a tutorial on your machine is to set up a development environment.</span></span>
<span data-ttu-id="f4a38-105">В руководстве .NET по созданию программы [Hello World за 10 минут](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) содержатся инструкции по настройке локальной среды разработки в macOS, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="f4a38-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span>

<span data-ttu-id="f4a38-106">Кроме того, вы можете установить [пакет SDK для .NET Core](https://dotnet.microsoft.com/download) и [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="f4a38-106">Alternatively, you can install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="f4a38-107">Базовый поток разработки приложения</span><span class="sxs-lookup"><span data-stu-id="f4a38-107">Basic application development flow</span></span>

<span data-ttu-id="f4a38-108">Чтобы создать приложения, выполните команду [`dotnet new`](../../../core/tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="f4a38-108">You'll create applications using the [`dotnet new`](../../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="f4a38-109">Эта команда создает файлы и ресурсы, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="f4a38-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="f4a38-110">Во всех ознакомительных руководствах по C# используется тип приложения `console`.</span><span class="sxs-lookup"><span data-stu-id="f4a38-110">The introduction to C# tutorials all use the `console` application type.</span></span> <span data-ttu-id="f4a38-111">Освоив описанные здесь основы, вы сможете перейти и к другим типам приложений.</span><span class="sxs-lookup"><span data-stu-id="f4a38-111">Once you've got the basics, you can expand to other application types.</span></span>

<span data-ttu-id="f4a38-112">Выполните команду [`dotnet build`](../../../core/tools/dotnet-build.md), чтобы создать исполняемый файл. Затем запустите исполняемый файла с помощью команды [`dotnet run`](../../../core/tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="f4a38-112">The other commands you'll use are [`dotnet build`](../../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-tutorial"></a><span data-ttu-id="f4a38-113">Выбор руководства</span><span class="sxs-lookup"><span data-stu-id="f4a38-113">Pick your tutorial</span></span>

<span data-ttu-id="f4a38-114">Вы можете начать изучение с любого из следующих руководств:</span><span class="sxs-lookup"><span data-stu-id="f4a38-114">You can start with any of the following tutorials:</span></span>

## <a name="numbers-in-c"></a>[<span data-ttu-id="f4a38-115">Числа в C#</span><span class="sxs-lookup"><span data-stu-id="f4a38-115">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="f4a38-116">Из руководства [Числа в C#](numbers-in-csharp-local.md) вы узнаете, как на компьютере хранятся числа и как выполнять вычисления с разными числовыми типами.</span><span class="sxs-lookup"><span data-stu-id="f4a38-116">In the [Numbers in C#](numbers-in-csharp-local.md) tutorial, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="f4a38-117">Вы ознакомитесь с основами округления и научитесь выполнять математические вычисления с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="f4a38-117">You'll learn the basics of rounding and how to perform mathematical calculations using C#.</span></span>

<span data-ttu-id="f4a38-118">В этом руководстве предполагается, что вы уже прошли занятие [Hello World](hello-world.yml).</span><span class="sxs-lookup"><span data-stu-id="f4a38-118">This tutorial assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loops"></a>[<span data-ttu-id="f4a38-119">Ветви и циклы</span><span class="sxs-lookup"><span data-stu-id="f4a38-119">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="f4a38-120">В руководстве [Ветви и циклы](branches-and-loops-local.md) представлены общие принципы организации ветвления кода в зависимости от значений, хранящихся в переменных.</span><span class="sxs-lookup"><span data-stu-id="f4a38-120">The [Branches and loops](branches-and-loops-local.md) tutorial teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="f4a38-121">Вы узнаете, что такое поток управления, являющийся основой принятия решений и выбора различных действий в программах.</span><span class="sxs-lookup"><span data-stu-id="f4a38-121">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span>

<span data-ttu-id="f4a38-122">В этом руководстве предполагается, что вы уже прошли занятия [Hello World](hello-world.yml) и [Числа в C#](numbers-in-csharp-local.md).</span><span class="sxs-lookup"><span data-stu-id="f4a38-122">This tutorial assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collection"></a>[<span data-ttu-id="f4a38-123">Коллекция списков</span><span class="sxs-lookup"><span data-stu-id="f4a38-123">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="f4a38-124">Занятие [Коллекция списков](arrays-and-collections.md) содержит обзор типа "Коллекция списков", в котором хранятся последовательности данных.</span><span class="sxs-lookup"><span data-stu-id="f4a38-124">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="f4a38-125">Вы узнаете, как добавлять и удалять элементы, выполнять их поиск и сортировать списки.</span><span class="sxs-lookup"><span data-stu-id="f4a38-125">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="f4a38-126">Вы ознакомитесь с различными типами списков.</span><span class="sxs-lookup"><span data-stu-id="f4a38-126">You'll explore different kinds of lists.</span></span>

<span data-ttu-id="f4a38-127">В этом руководстве предполагается, что вы уже прошли перечисленные выше занятия.</span><span class="sxs-lookup"><span data-stu-id="f4a38-127">This tutorial assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classes"></a>[<span data-ttu-id="f4a38-128">Общие сведения о классах</span><span class="sxs-lookup"><span data-stu-id="f4a38-128">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="f4a38-129">Это заключительное ознакомительное руководство по C# можно изучить только на локальном компьютере, используя настроенную среду разработки и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f4a38-129">This final introduction to C# tutorial is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="f4a38-130">Вы создадите консольное приложение и изучите основные объектно-ориентированные функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="f4a38-130">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
