---
title: Руководство по языку F#
description: 'Это руководство предоставляет обзор различных учебных материалов для языка F #, это функциональный язык программирования, работающей на платформе .NET.'
author: jackfoxy
ms.author: phcart
ms.date: 03/19/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: a101233f396368c0bc25937c49f77699cb9f8cf2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="f-guide"></a><span data-ttu-id="bb1ea-103">Руководство по языку F#</span><span class="sxs-lookup"><span data-stu-id="bb1ea-103">F# Guide</span></span>

<span data-ttu-id="bb1ea-104">F # — функциональной язык программирования, который выполняется на платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="bb1ea-105">Он также имеет полную поддержку для объектов, позволяя функциональной blend и программирование объекта прагматичное использование решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="bb1ea-106">F # — о производительности сущность.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="bb1ea-107">Поддержка инструментами F # является универсальной, так и полного дополнительных возможностей.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="bb1ea-108">Изучение F #</span><span class="sxs-lookup"><span data-stu-id="bb1ea-108">Learning F#</span></span> #

<span data-ttu-id="bb1ea-109">[Учебник по F #](tour.md) предоставляет обзор функций основной язык с большим количеством примеров кода.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="bb1ea-110">Рекомендуется, если впервые введены в F # и чтобы понять, как работает язык.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="bb1ea-111">[Начало работы с F # в Visual Studio](get-started/get-started-visual-studio.md) Если вы используете Windows и полное взаимодействие IDE Visual Studio (среда разработки Integraded).</span><span class="sxs-lookup"><span data-stu-id="bb1ea-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="bb1ea-112">[Начало работы с F # в Visual Studio для Mac](get-started/get-started-with-visual-studio-for-mac.md) при работе на macOS и хотите использовать Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="bb1ea-113">[Начало работы с F # в Visual Studio Code](get-started/get-started-vscode.md) Если требуется компактное между различными платформами и возникают упакованные функции интегрированной среды разработки.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="bb1ea-114">[Начало работы с F # с .NET Core CLI](get-started/get-started-command-line.md) Если требуется использование средств командной строки.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

<span data-ttu-id="bb1ea-115">[Начало работы с F # и Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) для мобильных устройств программирование на F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-115">[Get started with F# and Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) for mobile programming with F#.</span></span>

## <a name="references"></a><span data-ttu-id="bb1ea-116">Ссылки</span><span class="sxs-lookup"><span data-stu-id="bb1ea-116">References</span></span>

<span data-ttu-id="bb1ea-117">[Справочник по языку F #](language-reference/index.md) является официальным и полную ссылку для всех компонентов языка F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-117">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="bb1ea-118">Каждой статьи о синтаксисе и примеры кода.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-118">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="bb1ea-119">В оглавлении можно использовать панель фильтра для поиска конкретных статей.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-119">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="bb1ea-120">[Справочник по основной библиотеке F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) является Справочник по API для основной библиотеки F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-120">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>


## <a name="additional-guides"></a><span data-ttu-id="bb1ea-121">Дополнительные руководства</span><span class="sxs-lookup"><span data-stu-id="bb1ea-121">Additional guides</span></span>

<span data-ttu-id="bb1ea-122">[F # для удовольствия и прибыли](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) книга в очень подробные на изучение F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-122">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="bb1ea-123">Его содержимое и автор любимое сообществом F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-123">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="bb1ea-124">Целевая аудитория — в первую очередь разработчики объектно-ориентированного программирования фоне.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-124">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="bb1ea-125">[Wikibook программирования F #](https://en.wikibooks.org/wiki/F_Sharp_Programming) является wikibook обучения F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-125">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="bb1ea-126">Это также продукта сообщества F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-126">It is also a product of the F# community.</span></span> <span data-ttu-id="bb1ea-127">Целевая аудитория — людей, которые являются новыми в F #, с небольшим фона объектно-ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-127">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="bb1ea-128">Сведения о F # видео</span><span class="sxs-lookup"><span data-stu-id="bb1ea-128">Learn F# through videos</span></span>

<span data-ttu-id="bb1ea-129">[Учебник по F # на YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) , отлично сведения о F # с помощью Visual Studio, показывающая большое количество демонстрации в ходе 1,5 часа.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-129">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="bb1ea-130">Целевая аудитория — Visual Studio разработчиков, незнакомых с F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-130">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="bb1ea-131">[Введение в программирование на F #](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) является отличным серии видеороликов, использует в качестве основной редактор кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-131">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="bb1ea-132">Серия видеоматериалов начинается с nothing и заканчивается Создание текстовых RPG игру.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-132">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="bb1ea-133">Целевая аудитория — разработчиков, которые предпочитают кода Visual Studio (или упрощенных IDE) и не знакомы с F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-133">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="bb1ea-134">[Новые возможности Visual Studio 2017 г. для F # для разработчиков](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) видео курс, в котором представлены некоторые новые функции для языка F # в Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-134">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="bb1ea-135">Целевая аудитория — Visual Studio разработчиков, незнакомых с F #.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-135">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="bb1ea-136">Другие полезные ресурсы</span><span class="sxs-lookup"><span data-stu-id="bb1ea-136">Other useful resources</span></span>

<span data-ttu-id="bb1ea-137">[Веб-сайта для F # фрагменты](http://www.fssnip.net) содержит набор больших фрагментов кода в F #, — от начинающих до высокой Дополнительно фрагменты практически что угодно.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-137">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="bb1ea-138">[Slack Foundation программного обеспечения F #](http://fsharp.org/guides/slack/) — отличное место для начинающих и экспертов одинаково, высокой активностью и обладает некоторыми мире наиболее F # программистов для разговора.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-138">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="bb1ea-139">Корпорация Майкрософт рекомендует присоединения.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-139">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="bb1ea-140">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="bb1ea-140">The F# Software Foundation</span></span>

<span data-ttu-id="bb1ea-141">Несмотря на то, что Майкрософт является основным разработчиком его средства в Visual Studio и языке F #, F # также поддерживаемый независимых foundation, F # программного обеспечения Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="bb1ea-141">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="bb1ea-142">В задачи F# Software Foundation входит продвижение, защита и совершенствование языка программирования F#, а также поддержка и расширение международного сообщества программистов F#.</span><span class="sxs-lookup"><span data-stu-id="bb1ea-142">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="bb1ea-143">Узнать дополнительные сведения и принять участие в этой работе можно на сайте [fsharp.org](http://fsharp.org). Он распространяется бесплатно присоединить и сеть разработчиков F # в foundation является то, что вы не хотите пропустите!</span><span class="sxs-lookup"><span data-stu-id="bb1ea-143">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>
