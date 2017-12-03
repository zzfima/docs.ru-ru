---
title: "Руководство по языку F#"
description: "Дополнительные сведения о F #, это функциональный язык программирования, работающей на платформе .NET."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 12/01/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 45f5d2ca794ccea7a35cf6c0bf9d58a3e6500453
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="f-guide"></a><span data-ttu-id="d40f1-104">Руководство по языку F#</span><span class="sxs-lookup"><span data-stu-id="d40f1-104">F# Guide</span></span>

<span data-ttu-id="d40f1-105">F # является функциональным языком программирования, которая выполняется на платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="d40f1-105">F# is a functional programming language which runs on .NET.</span></span>  <span data-ttu-id="d40f1-106">Помимо поддержки конструкций функционального программирования он также имеет возможности программирования объектов.</span><span class="sxs-lookup"><span data-stu-id="d40f1-106">In addition to supporting functional programming constructs, it also has object programming capabilities.</span></span>  <span data-ttu-id="d40f1-107">Делает этот гибридом функционального программирования с объектно ориентированные возможности F # прагматичное использование языка для выполнения любой задачи.</span><span class="sxs-lookup"><span data-stu-id="d40f1-107">This hybrid of functional programming with object-oriented capabilities makes F# a pragmatic language for accomplishing any task.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="d40f1-108">Если вы не знакомы с F #</span><span class="sxs-lookup"><span data-stu-id="d40f1-108">If You're New to F#</span></span> #

<span data-ttu-id="d40f1-109">Если вы не знакомы с F #, начинаются с [обзор языка F #](tour.md) получить общие сведения о языке и некоторые из его принципы программирования.</span><span class="sxs-lookup"><span data-stu-id="d40f1-109">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language and some of its programming concepts.</span></span>  <span data-ttu-id="d40f1-110">Если вы используете Visual Studio, шаблон учебного проекта содержит то же содержимое.</span><span class="sxs-lookup"><span data-stu-id="d40f1-110">If you're using Visual Studio, the Tutorial project template contains the same content.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="d40f1-111">Если у вас есть опыт работы с F #</span><span class="sxs-lookup"><span data-stu-id="d40f1-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="d40f1-112">Если вы знаете, как F # или хотите узнать больше о конкретных языковой конструкции, см. раздел [Справочник по языку](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="d40f1-112">If you know your way around F#, or want to learn more about a specific language construct, see the [Language Reference](language-reference/index.md).</span></span>  <span data-ttu-id="d40f1-113">Это подробное руководство по всех возможностей языка F #.</span><span class="sxs-lookup"><span data-stu-id="d40f1-113">It's a thorough guide of all F# language capabilities.</span></span>

<span data-ttu-id="d40f1-114">Кроме того [Справочник по основной библиотеке F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) — это отличный ресурс для изучения FSharp.Core основной библиотеки, являющийся частью F #.</span><span class="sxs-lookup"><span data-stu-id="d40f1-114">Additionally, the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is a great resource for learning about FSharp.Core, the core library which is a part of F#.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="d40f1-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="d40f1-115">The F# Software Foundation</span></span>

<span data-ttu-id="d40f1-116">Несмотря на то, что корпорация Майкрософт является основным разработчиком языка F # и его инструментарий, F # также поддерживаемый независимых foundation, F # программного обеспечения Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="d40f1-116">Although Microsoft is the primary developer of the F# language and its tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="d40f1-117">В задачи F# Software Foundation входит продвижение, защита и совершенствование языка программирования F#, а также поддержка и расширение международного сообщества программистов F#.</span><span class="sxs-lookup"><span data-stu-id="d40f1-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="d40f1-118">Узнать дополнительные сведения и принять участие в этой работе можно на сайте [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="d40f1-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="d40f1-119">Документация</span><span class="sxs-lookup"><span data-stu-id="d40f1-119">Documentation</span></span>

* [<span data-ttu-id="d40f1-120">Учебники</span><span class="sxs-lookup"><span data-stu-id="d40f1-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="d40f1-121">[Функции как значения первого класса](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="d40f1-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="d40f1-122">Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="d40f1-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="d40f1-123">Справочные материалы по основной библиотеке F#</span><span class="sxs-lookup"><span data-stu-id="d40f1-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="d40f1-124">Ресурсы для ознакомления в Интернете</span><span class="sxs-lookup"><span data-stu-id="d40f1-124">Online Reading Resources</span></span>

* [<span data-ttu-id="d40f1-125">Gitbook об использовании F# для развлечений и работы</span><span class="sxs-lookup"><span data-stu-id="d40f1-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="d40f1-126">Вики-учебник по программированию на F#</span><span class="sxs-lookup"><span data-stu-id="d40f1-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="d40f1-127">Учебные видеоматериалы</span><span class="sxs-lookup"><span data-stu-id="d40f1-127">Video Learning Resources</span></span>

* [<span data-ttu-id="d40f1-128">Серия выпусков по введению в программирование на языке F# на YouTube</span><span class="sxs-lookup"><span data-stu-id="d40f1-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="d40f1-129">Серия выпусков по введению F# на FSharpTV</span><span class="sxs-lookup"><span data-stu-id="d40f1-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="d40f1-130">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="d40f1-130">Further Resources</span></span>

* [<span data-ttu-id="d40f1-131">Учебные материалы по F# на сайте fsharp.org</span><span class="sxs-lookup"><span data-stu-id="d40f1-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="d40f1-132">Веб-сайт с фрагментами кода F#</span><span class="sxs-lookup"><span data-stu-id="d40f1-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="d40f1-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="d40f1-133">F# Software Foundation</span></span>](http://fsharp.org)