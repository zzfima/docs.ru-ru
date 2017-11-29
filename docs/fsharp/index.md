---
title: "Руководство по языку F#"
description: "Дополнительные сведения о F # язык программирования, открытым исходным кодом языка для .NET, которая обеспечивает поддержку функционального программирования."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 4ddd77cef6cf70a63f1af81359d82eda27a01593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="f-guide"></a><span data-ttu-id="1de9a-104">Руководство по языку F#</span><span class="sxs-lookup"><span data-stu-id="1de9a-104">F# Guide</span></span>

<span data-ttu-id="1de9a-105">F# — это кроссплатформенный язык программирования с открытым исходным кодом для платформы .NET который обеспечивает первоклассную поддержку функционального программирования, а также объектно-ориентированного и императивного программирования.</span><span class="sxs-lookup"><span data-stu-id="1de9a-105">F# is a cross-platform, open source programming language for .NET which provides first-class support for functional programming, along with support of object-oriented and imperative programming.</span></span>  <span data-ttu-id="1de9a-106">Компилятор и инструменты Visual F# представляют собой реализацию языка F# от корпорации Майкрософт, что делает F# важным элементом платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="1de9a-106">The Visual F# compiler and tooling are Microsoft's implementation and tooling for the F# programming language, making F# a first-class member of .NET.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="1de9a-107">Если вы не знакомы с F #</span><span class="sxs-lookup"><span data-stu-id="1de9a-107">If You're New to F#</span></span> #

<span data-ttu-id="1de9a-108">Если вы не знакомы с F #, начинаются с [обзор языка F #](tour.md) для получения обзора языка.</span><span class="sxs-lookup"><span data-stu-id="1de9a-108">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language.</span></span>

<span data-ttu-id="1de9a-109">Кроме того, рекомендуется изучить [функции как значения первого класса](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> научиться понятия функционального программирования, которые необходимы для работы с F #.</span><span class="sxs-lookup"><span data-stu-id="1de9a-109">It's also recommended that you go through the [Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> to learn Functional Programming concepts which are essential to working with F#.</span></span>

<span data-ttu-id="1de9a-110">[Учебники](tutorials/getting-started/index.md) также содержат пошаговые инструкции по разным функциям языка для пользователей различной квалификации.</span><span class="sxs-lookup"><span data-stu-id="1de9a-110">The [Tutorials](tutorials/getting-started/index.md) also have step-by-step guides for various skill levels and features of the language.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="1de9a-111">Если у вас есть опыт работы с F #</span><span class="sxs-lookup"><span data-stu-id="1de9a-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="1de9a-112">Если вы уже изучили F#, то найдете много полезной информации в [справочнике по языку](language-reference/index.md), где каждый из аспектов языка тщательно задокументирован и снабжен многочисленными примерами кода.</span><span class="sxs-lookup"><span data-stu-id="1de9a-112">If you know your way around F#, you'll find a lot of use in the [Language Reference](language-reference/index.md), which documents each aspect of the language thoroughly, supplemented by numerous code samples.</span></span>  <span data-ttu-id="1de9a-113">Кроме того, много полезного вы найдете в статье [Справочные материалы по основной библиотеке F#](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference).</span><span class="sxs-lookup"><span data-stu-id="1de9a-113">You'll also find a lot of use in the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference).</span></span>  <span data-ttu-id="1de9a-114">Справочнике библиотеки ядра F # со временем перемещаются из MSDN и в эти документы текущего.</span><span class="sxs-lookup"><span data-stu-id="1de9a-114">The F# Core Library Reference will eventually move away from MSDN and into these current docs.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="1de9a-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="1de9a-115">The F# Software Foundation</span></span>

<span data-ttu-id="1de9a-116">Хотя основным разработчиком языка F# и инструментария Visual F# является корпорация Майкрософт, язык F# также развивается силами независимой платформы — F# Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="1de9a-116">Although Microsoft is the primary developer of the F# language and Visual F# Tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="1de9a-117">В задачи F# Software Foundation входит продвижение, защита и совершенствование языка программирования F#, а также поддержка и расширение международного сообщества программистов F#.</span><span class="sxs-lookup"><span data-stu-id="1de9a-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="1de9a-118">Узнать дополнительные сведения и принять участие в этой работе можно на сайте [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="1de9a-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="1de9a-119">Документация</span><span class="sxs-lookup"><span data-stu-id="1de9a-119">Documentation</span></span>

* [<span data-ttu-id="1de9a-120">Учебники</span><span class="sxs-lookup"><span data-stu-id="1de9a-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="1de9a-121">[Функции как значения первого класса](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="1de9a-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="1de9a-122">Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="1de9a-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="1de9a-123">Справочные материалы по основной библиотеке F#</span><span class="sxs-lookup"><span data-stu-id="1de9a-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="1de9a-124">Ресурсы для ознакомления в Интернете</span><span class="sxs-lookup"><span data-stu-id="1de9a-124">Online Reading Resources</span></span>

* [<span data-ttu-id="1de9a-125">Gitbook об использовании F# для развлечений и работы</span><span class="sxs-lookup"><span data-stu-id="1de9a-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="1de9a-126">Вики-учебник по программированию на F#</span><span class="sxs-lookup"><span data-stu-id="1de9a-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="1de9a-127">Учебные видеоматериалы</span><span class="sxs-lookup"><span data-stu-id="1de9a-127">Video Learning Resources</span></span>

* [<span data-ttu-id="1de9a-128">Серия выпусков по введению в программирование на языке F# на YouTube</span><span class="sxs-lookup"><span data-stu-id="1de9a-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="1de9a-129">Серия выпусков по введению F# на FSharpTV</span><span class="sxs-lookup"><span data-stu-id="1de9a-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="1de9a-130">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="1de9a-130">Further Resources</span></span>

* [<span data-ttu-id="1de9a-131">Учебные материалы по F# на сайте fsharp.org</span><span class="sxs-lookup"><span data-stu-id="1de9a-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="1de9a-132">Веб-сайт с фрагментами кода F#</span><span class="sxs-lookup"><span data-stu-id="1de9a-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="1de9a-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="1de9a-133">F# Software Foundation</span></span>](http://fsharp.org)
