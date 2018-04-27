---
title: Новые возможности C# — руководство по C#
description: Как развивается язык C#
keywords: C#, последние функции, новые возможности, Roslyn
author: BillWagner
ms.author: wiwagn
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: d66f835d57f43d2016d3b20e2205e0052d064acb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="whats-new-in-c"></a><span data-ttu-id="7ad2f-104">Новые возможности C#</span><span class="sxs-lookup"><span data-stu-id="7ad2f-104">What's new in C#</span></span> #

<span data-ttu-id="7ad2f-105">Эта страница содержит план новых возможностей в каждой основной версии языка C#.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="7ad2f-106">Перейдя по ссылкам ниже, вы сможете получить подробные сведения по основным возможностям, добавленным в каждом выпуске.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-106">The following links provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ad2f-107">В некоторых возможностях используются типы и методы в *стандартной библиотеке* языка C#,</span><span class="sxs-lookup"><span data-stu-id="7ad2f-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="7ad2f-108">например, обработка исключений.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-108">One example is exception processing.</span></span> <span data-ttu-id="7ad2f-109">Каждая инструкция и выражение `throw` проверяется, чтобы убедиться, что вызываемый объект является производным от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="7ad2f-110">Аналогичным образом каждая инструкция `catch` проверяется, чтобы убедиться, что перехваченный тип является производным от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="7ad2f-111">В каждой версии могут добавляться новые требования.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-111">Each version may add new requirements.</span></span> <span data-ttu-id="7ad2f-112">Чтобы использовать новейшие возможности языка в старой среде, может потребоваться установить определенные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="7ad2f-113">Эти зависимости описаны на странице для каждой конкретной версии.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-113">These dependencies are documented in the page for each specific version.</span></span> <span data-ttu-id="7ad2f-114">Дополнительные сведения о связи между языком и библиотекой, а также общие сведения о такой зависимости см. [здесь](relationships-between-language-and-library.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 


* <span data-ttu-id="7ad2f-115">[C# 7.2](csharp-7-2.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-115">[C# 7.2](csharp-7-2.md):</span></span>
    - <span data-ttu-id="7ad2f-116">На этой странице описываются новейшие функции в языке C#.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="7ad2f-117">C# 7.2 сейчас доступен в [Visual Studio 2017 версии 15.5](https://www.visualstudio.com/vs/whatsnew/) и в [пакете SDK для .NET Core 2.0](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-117">C# 7.2 is currently available in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="7ad2f-118">[C# 7.1](csharp-7-1.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-118">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="7ad2f-119">На этой странице описываются функции в C# 7.1.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-119">This page describes the features in C# 7.1.</span></span> <span data-ttu-id="7ad2f-120">Эти функции были добавлены в [Visual Studio 2017 версии 15.3](https://www.visualstudio.com/vs/whatsnew/) и в [пакет SDK для .NET Core 2.0](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-120">These features were added in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="7ad2f-121">[C# 7.0](csharp-7.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-121">[C# 7.0](csharp-7.md):</span></span>
    - <span data-ttu-id="7ad2f-122">На этой странице описываются функции, добавленные в C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-122">This page describes the features added in C# 7.0.</span></span> <span data-ttu-id="7ad2f-123">Они были добавлены в [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/), [.NET Core 1.0](../../core/whats-new/index.md) и более поздние версии.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-123">These features were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="7ad2f-124">[C# 6](csharp-6.md)</span><span class="sxs-lookup"><span data-stu-id="7ad2f-124">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="7ad2f-125">На этой странице описываются функции, добавленные в C# 6.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-125">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="7ad2f-126">Эти функции доступны в Visual Studio 2015 для разработчиков Windows и в .NET Core 1.0 для разработчиков, исследующих C# на macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-126">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="7ad2f-127">[Кроссплатформенная поддержка](../../core/index.md)</span><span class="sxs-lookup"><span data-stu-id="7ad2f-127">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="7ad2f-128">Благодаря поддержке .NET Core язык C# работает на многих платформах.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-128">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="7ad2f-129">Если вы хотите попробовать C# на macOS или на одном из множества поддерживаемых дистрибутивов Linux, узнайте больше о .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-129">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="7ad2f-130">Предыдущие версии</span><span class="sxs-lookup"><span data-stu-id="7ad2f-130">Previous Versions</span></span>
<span data-ttu-id="7ad2f-131">Ниже перечислены основные функции, представленные в предыдущих версиях языка C# и Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-131">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="7ad2f-132">Visual Studio .NET 2013</span><span class="sxs-lookup"><span data-stu-id="7ad2f-132">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="7ad2f-133">Эта версия Visual Studio включает исправления ошибок, повышение производительности и предварительные версии технологий платформы компилятора .NET ("Roslyn"), который стал <!--Link to ../roslyn/index.md-->пакетом SDK для платформы компилятора .NET.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-133">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="7ad2f-134">C# 5, Visual Studio .NET 2012</span><span class="sxs-lookup"><span data-stu-id="7ad2f-134">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="7ad2f-135">`Async` / `await`, и атрибуты [сведений о вызывающем объекте](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-135">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="7ad2f-136">C# 4, Visual Studio .NET 2010</span><span class="sxs-lookup"><span data-stu-id="7ad2f-136">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="7ad2f-137">`Dynamic`, [именованные аргументы](../programming-guide/classes-and-structs/named-and-optional-arguments.md), дополнительные параметры и [ковариации и контрвариантность](../programming-guide/concepts/covariance-contravariance/index.md) в универсальных шаблонах.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-137">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="7ad2f-138">C# 3, Visual Studio .NET 2008</span><span class="sxs-lookup"><span data-stu-id="7ad2f-138">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="7ad2f-139">Инициализаторы объектов и коллекций, лямбда-выражения, методы расширений, анонимные типы, автоматические свойства, вывод локального типа `var` и [LINQ](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-139">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="7ad2f-140">C# 2, Visual Studio .NET 2005</span><span class="sxs-lookup"><span data-stu-id="7ad2f-140">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="7ad2f-141">Анонимные методы, универсальные шаблоны, типы, допускающие значение NULL, итераторы и приостановки, классы `static`, ковариации и контрвариантность для делегатов.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-141">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="7ad2f-142">C# 1.1, Visual Studio .NET 2003</span><span class="sxs-lookup"><span data-stu-id="7ad2f-142">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="7ad2f-143">`#line` pragma и комментарии XML-документации.</span><span class="sxs-lookup"><span data-stu-id="7ad2f-143">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="7ad2f-144">C# 1, Visual Studio .NET 2002</span><span class="sxs-lookup"><span data-stu-id="7ad2f-144">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="7ad2f-145">Первый выпуск [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="7ad2f-145">The first release of [C#](../csharp.md).</span></span>   
