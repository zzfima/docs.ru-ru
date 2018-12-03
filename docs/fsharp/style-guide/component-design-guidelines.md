---
title: 'Рекомендации по проектированию компонентов F #'
description: 'Дополнительные рекомендации по написанию компонентов F #, предназначенный для использования другими вызывающими объектами.'
ms.date: 05/14/2018
ms.openlocfilehash: 446cba0f810af9517b655ef5741ddf7a919676d5
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43488291"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="c7dcb-103">Рекомендации по проектированию компонентов F #</span><span class="sxs-lookup"><span data-stu-id="c7dcb-103">F# component design guidelines</span></span>

<span data-ttu-id="c7dcb-104">Этот документ представляет собой набор рекомендации по проектированию компонентов F # программирования, исходя из F # рекомендации по проектированию компонентов, v14, Microsoft Research и [другая версия](https://fsharp.org/specs/component-design-guidelines/) изначально проверенный и обслуживается F # Software Foundation.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="c7dcb-105">В этом документе предполагается, что вы знакомы с программирование на F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="c7dcb-106">Выражаем благодарность сообщества F # за их вклад и полезные отзывы на различные версии данного руководства.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="c7dcb-107">Обзор</span><span class="sxs-lookup"><span data-stu-id="c7dcb-107">Overview</span></span>

<span data-ttu-id="c7dcb-108">В этом документе рассматриваются некоторые вопросы, относящиеся к разработке для компонента F # и написанию кода.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="c7dcb-109">Компонент может означать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="c7dcb-110">Слой в проекте F #, которая имеет внешних потребителей в рамках проекта.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="c7dcb-111">Библиотека, предназначенными для использования в коде F # за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="c7dcb-112">Библиотека, предназначенный для использования с любым языком программирования .NET за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="c7dcb-113">Библиотеки, предназначенные для распространения с помощью репозитория пакетов, таких как [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="c7dcb-114">Методы, описанные в этой статье выполните [пять принципов хорошей кода F #](index.md#five-principles-of-good-f-code)и таким образом использовать функций и объектов, программирование соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="c7dcb-115">Независимо от того, методику конструктор компонента и библиотека сталкивается ряд практических и прозаическом проблем при попытке создать API, который проще всего использовать разработчиками.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="c7dcb-116">Conscientious применения [рекомендации по разработке библиотек .NET](../../standard/design-guidelines/index.md) будет управлять процессом к созданию согласованный набор API, которые являются приятной для использования.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="c7dcb-117">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="c7dcb-117">General guidelines</span></span>

<span data-ttu-id="c7dcb-118">Существует несколько универсальных рекомендаций, которые применяются к библиотек F #, независимо от того, целевая аудитория для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="c7dcb-119">Дополнительные рекомендации по разработке библиотек .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="c7dcb-120">Независимо от типа F # кодирования, вы выполняете, важно иметь опыт работы с [рекомендации по разработке библиотек .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="c7dcb-121">Большинство других F # программистов .NET будет ознакомьтесь с рекомендациями и ожидать, что код .NET в соответствии с их.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="c7dcb-122">Рекомендации по разработке библиотек .NET предоставляют общие рекомендации по именованию, конструирование классов и интерфейсов, член конструктора (свойства, методы, события, и т.д.) и сведения и полезные первый точку ссылки для разнообразных руководство по проектированию.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="c7dcb-123">Добавьте в код комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="c7dcb-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="c7dcb-124">XML-документации в открытых API убедитесь, что пользователи могут получить великолепное Intellisense и кратких сведений, с помощью этих типов и членов и включить создание документации файлов для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="c7dcb-125">См. в разделе [XML-документации](../language-reference/xml-documentation.md) о различных XML-теги, которые могут использоваться для дополнительной разметки внутри комментариев xmldoc.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="c7dcb-126">С помощью комментариев XML краткая форма (`/// comment`), или стандартные XML-комментариев (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="c7dcb-127">Рассмотрите возможность использования файлов явные сигнатур (расширение FSI) для стабильной библиотеки и API-интерфейсы компонента</span><span class="sxs-lookup"><span data-stu-id="c7dcb-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="c7dcb-128">С помощью явных подписей файлов в библиотеку F # предоставляет краткий сводку открытый API, они также располагаются позволяет гарантировать, что вы знаете полного открытого области библиотеки, а также предоставляет четкого разделения между общедоступной документации по и внутренние сведения о реализации.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="c7dcb-129">Обратите внимание на то, что файлы сигнатур добавить трения изменение открытого API-интерфейса, при необходимости вносить изменения в файлах и реализации и подпись.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="c7dcb-130">Таким образом файлы подписей должны обычно только быть предоставлены при API становятся упрочило и больше не может быть значительно изменить.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="c7dcb-131">Всегда следуйте рекомендациям по использованию строк в .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="c7dcb-132">Выполните [советы и рекомендации по использованию строк в .NET](../../standard/base-types/best-practices-strings.md) рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="c7dcb-133">В частности, всегда явно указывать *региональные намерение* в преобразование и сравнение строк (если применимо).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="c7dcb-134">Рекомендации по F #-с выходом библиотеки</span><span class="sxs-lookup"><span data-stu-id="c7dcb-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="c7dcb-135">В этом разделе представлены рекомендации по разработке общедоступных F #-с выходом библиотеки; то есть библиотеки, предоставляя открытый API-интерфейсы, которые должны использоваться разработчиков F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="c7dcb-136">Существует множество рекомендаций по разработке библиотеки применимо специально для F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="c7dcb-137">В случае отсутствия определенные рекомендации, выполните рекомендации по разработке библиотек .NET являются резервной рекомендации.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="c7dcb-138">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="c7dcb-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="c7dcb-139">Используйте соглашения об именовании и регистр букв .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="c7dcb-140">Соглашения об именовании и регистр букв .NET учтена в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="c7dcb-141">Существует небольшой дополнения для включения конструкций F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="c7dcb-142">Конструкция</span><span class="sxs-lookup"><span data-stu-id="c7dcb-142">Construct</span></span> | <span data-ttu-id="c7dcb-143">Case</span><span class="sxs-lookup"><span data-stu-id="c7dcb-143">Case</span></span> | <span data-ttu-id="c7dcb-144">Отделение</span><span class="sxs-lookup"><span data-stu-id="c7dcb-144">Part</span></span> | <span data-ttu-id="c7dcb-145">Примеры</span><span class="sxs-lookup"><span data-stu-id="c7dcb-145">Examples</span></span> | <span data-ttu-id="c7dcb-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7dcb-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="c7dcb-147">Конкретные типы</span><span class="sxs-lookup"><span data-stu-id="c7dcb-147">Concrete types</span></span> | <span data-ttu-id="c7dcb-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-148">PascalCase</span></span> | <span data-ttu-id="c7dcb-149">Существительное / прилагательными</span><span class="sxs-lookup"><span data-stu-id="c7dcb-149">Noun/ adjective</span></span> | <span data-ttu-id="c7dcb-150">Список, Double, сложный</span><span class="sxs-lookup"><span data-stu-id="c7dcb-150">List, Double, Complex</span></span> | <span data-ttu-id="c7dcb-151">Конкретные типы структур, классов, перечислений, делегаты, записей и объединений.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="c7dcb-152">То, что имена типов традиционно нижний регистр в OCaml, F # введена новая схема именования .NET для типов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="c7dcb-153">библиотеки DLL</span><span class="sxs-lookup"><span data-stu-id="c7dcb-153">DLLs</span></span>           | <span data-ttu-id="c7dcb-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-154">PascalCase</span></span> |                 | <span data-ttu-id="c7dcb-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c7dcb-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="c7dcb-156">Объединения тегов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-156">Union tags</span></span>     | <span data-ttu-id="c7dcb-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-157">PascalCase</span></span> | <span data-ttu-id="c7dcb-158">Существительное</span><span class="sxs-lookup"><span data-stu-id="c7dcb-158">Noun</span></span> | <span data-ttu-id="c7dcb-159">Некоторые из них, добавить, успех</span><span class="sxs-lookup"><span data-stu-id="c7dcb-159">Some, Add, Success</span></span> | <span data-ttu-id="c7dcb-160">Не используйте префикс общедоступных интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="c7dcb-161">При необходимости использовать префикс при внутренней, такие как \`\`\`введите команды = TAlpha</span><span class="sxs-lookup"><span data-stu-id="c7dcb-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="c7dcb-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="c7dcb-162">TBeta</span></span> | <span data-ttu-id="c7dcb-163">TDelta.\`\`\`</span><span class="sxs-lookup"><span data-stu-id="c7dcb-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="c7dcb-164">событие</span><span class="sxs-lookup"><span data-stu-id="c7dcb-164">Event</span></span>          | <span data-ttu-id="c7dcb-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-165">PascalCase</span></span> | <span data-ttu-id="c7dcb-166">Команда</span><span class="sxs-lookup"><span data-stu-id="c7dcb-166">Verb</span></span> | <span data-ttu-id="c7dcb-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="c7dcb-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="c7dcb-168">Исключения</span><span class="sxs-lookup"><span data-stu-id="c7dcb-168">Exceptions</span></span>     | <span data-ttu-id="c7dcb-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-169">PascalCase</span></span> |      | <span data-ttu-id="c7dcb-170">WebException</span><span class="sxs-lookup"><span data-stu-id="c7dcb-170">WebException</span></span> | <span data-ttu-id="c7dcb-171">Имя должно заканчиваться на «Exception».</span><span class="sxs-lookup"><span data-stu-id="c7dcb-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="c7dcb-172">Поле</span><span class="sxs-lookup"><span data-stu-id="c7dcb-172">Field</span></span>          | <span data-ttu-id="c7dcb-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-173">PascalCase</span></span> | <span data-ttu-id="c7dcb-174">Существительное</span><span class="sxs-lookup"><span data-stu-id="c7dcb-174">Noun</span></span> | <span data-ttu-id="c7dcb-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="c7dcb-175">CurrentName</span></span>  | |
| <span data-ttu-id="c7dcb-176">Типы интерфейса</span><span class="sxs-lookup"><span data-stu-id="c7dcb-176">Interface types</span></span> |  <span data-ttu-id="c7dcb-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-177">PascalCase</span></span> | <span data-ttu-id="c7dcb-178">Существительное / прилагательными</span><span class="sxs-lookup"><span data-stu-id="c7dcb-178">Noun/ adjective</span></span> | <span data-ttu-id="c7dcb-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="c7dcb-179">IDisposable</span></span> | <span data-ttu-id="c7dcb-180">Имя должно начинаться с «I».</span><span class="sxs-lookup"><span data-stu-id="c7dcb-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="c7dcb-181">Метод</span><span class="sxs-lookup"><span data-stu-id="c7dcb-181">Method</span></span> |  <span data-ttu-id="c7dcb-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-182">PascalCase</span></span> |  <span data-ttu-id="c7dcb-183">Команда</span><span class="sxs-lookup"><span data-stu-id="c7dcb-183">Verb</span></span> | <span data-ttu-id="c7dcb-184">ToString</span><span class="sxs-lookup"><span data-stu-id="c7dcb-184">ToString</span></span> | |
| <span data-ttu-id="c7dcb-185">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c7dcb-185">Namespace</span></span> | <span data-ttu-id="c7dcb-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-186">PascalCase</span></span> | | <span data-ttu-id="c7dcb-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="c7dcb-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="c7dcb-188">Обычно используется `<Organization>.<Technology>[.<Subnamespace>]`, но удалить организации, если эта технология не зависит от организации.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="c7dcb-189">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7dcb-189">Parameters</span></span> | <span data-ttu-id="c7dcb-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-190">camelCase</span></span> | <span data-ttu-id="c7dcb-191">Существительное</span><span class="sxs-lookup"><span data-stu-id="c7dcb-191">Noun</span></span> |  <span data-ttu-id="c7dcb-192">Имя типа, преобразование, диапазон</span><span class="sxs-lookup"><span data-stu-id="c7dcb-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="c7dcb-193">Разрешить значения (внутренний)</span><span class="sxs-lookup"><span data-stu-id="c7dcb-193">let values (internal)</span></span> | <span data-ttu-id="c7dcb-194">camelCase или PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-194">camelCase or PascalCase</span></span> | <span data-ttu-id="c7dcb-195">Существительное-глагол</span><span class="sxs-lookup"><span data-stu-id="c7dcb-195">Noun/ verb</span></span> |  <span data-ttu-id="c7dcb-196">getValue myTable</span><span class="sxs-lookup"><span data-stu-id="c7dcb-196">getValue, myTable</span></span> |
| <span data-ttu-id="c7dcb-197">Разрешить значения (внешний)</span><span class="sxs-lookup"><span data-stu-id="c7dcb-197">let values (external)</span></span> | <span data-ttu-id="c7dcb-198">camelCase или PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-198">camelCase or PascalCase</span></span> | <span data-ttu-id="c7dcb-199">Существительное глагол</span><span class="sxs-lookup"><span data-stu-id="c7dcb-199">Noun/verb</span></span>  | <span data-ttu-id="c7dcb-200">List.map Dates.Today</span><span class="sxs-lookup"><span data-stu-id="c7dcb-200">List.map, Dates.Today</span></span> | <span data-ttu-id="c7dcb-201">привязки let значения часто являются открытыми, при использовании традиционных функциональные шаблоны разработки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="c7dcb-202">Тем не менее обычно используется PascalCase, когда идентификатор может использоваться в других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="c7dcb-203">Свойство.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-203">Property</span></span>  | <span data-ttu-id="c7dcb-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-204">PascalCase</span></span>  | <span data-ttu-id="c7dcb-205">Существительное / прилагательными</span><span class="sxs-lookup"><span data-stu-id="c7dcb-205">Noun/ adjective</span></span>  | <span data-ttu-id="c7dcb-206">IsEndOfFile, BackColor</span><span class="sxs-lookup"><span data-stu-id="c7dcb-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="c7dcb-207">Логические свойства обычно использование является и могут и должны быть выразил, как и в IsEndOfFile, не IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="c7dcb-208">Избегать сокращений</span><span class="sxs-lookup"><span data-stu-id="c7dcb-208">Avoid abbreviations</span></span>

<span data-ttu-id="c7dcb-209">Рекомендации по .NET не рекомендует использовать сокращения (например, «использовать `OnButtonClick` вместо `OnBtnClick`«).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="c7dcb-210">Сокращений, таких как `Async` для «Асинхронной», которая допустима.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="c7dcb-211">Иногда это правило игнорируется для функционального программирования; например `List.iter` использует сокращение для «итерация».</span><span class="sxs-lookup"><span data-stu-id="c7dcb-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="c7dcb-212">По этой причине, использующие сокращения стремится скорректировать в большей степени в F #-к-программирование на F #, но по-прежнему обычно следует избегать в открытого компонента конструктора.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="c7dcb-213">Избежать конфликтов имен регистр</span><span class="sxs-lookup"><span data-stu-id="c7dcb-213">Avoid casing name collisions</span></span>

<span data-ttu-id="c7dcb-214">Рекомендации по .NET сказать, что регистр отдельно не может использоваться для однозначного определения конфликтов имен, так как некоторые языки клиента (например, Visual Basic), без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="c7dcb-215">Используйте акронимов, если это уместно</span><span class="sxs-lookup"><span data-stu-id="c7dcb-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="c7dcb-216">Акронимы, таких как XML, не являются сокращения и широко используются в библиотеках .NET в параметр формы (Xml).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="c7dcb-217">Только хорошо известного, широко признанный акронимов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="c7dcb-218">Использующие PascalCase для имен универсальных параметров</span><span class="sxs-lookup"><span data-stu-id="c7dcb-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="c7dcb-219">Использующие PascalCase для универсального параметра имен общедоступных интерфейсов API, в том числе для языка F #-с выходом библиотеки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="c7dcb-220">В частности, используйте имена, такие как `T`, `U`, `T1`, `T2` для произвольных универсальных параметров, а также при определенными именами имеет смысл, затем F #-имена, как использовать библиотеки с выходом `Key`, `Value`, `Arg`(но не к примеру, `TKey`).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="c7dcb-221">Использовать для открытых функций и значений в F # модули PascalCase или camelCase</span><span class="sxs-lookup"><span data-stu-id="c7dcb-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="c7dcb-222">camelCase используется для открытых функций, которые предназначены для использования неполное (например, `invalidArg`) и для «функции стандартной коллекции» (например, List.map).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="c7dcb-223">В обоих случаях имена функций действуют во многом аналогично ключевых слов на языке.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="c7dcb-224">Объект, тип и модуль разработки</span><span class="sxs-lookup"><span data-stu-id="c7dcb-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="c7dcb-225">Используйте пространства имен или модули для размещения типов и модули</span><span class="sxs-lookup"><span data-stu-id="c7dcb-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="c7dcb-226">Каждый файл F # в компоненте должно начинаться с объявлением пространства имен или объявлению модуля.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="c7dcb-227">или</span><span class="sxs-lookup"><span data-stu-id="c7dcb-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="c7dcb-228">Далее приведены различия между использованием модулей и пространств имен для организации кода верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="c7dcb-229">Пространства имен могут охватывать несколько файлов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="c7dcb-230">Пространства имен не может содержать функции F #, если они находятся в внутренним</span><span class="sxs-lookup"><span data-stu-id="c7dcb-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="c7dcb-231">Код для любого заданного модуля должны содержаться в одном файле</span><span class="sxs-lookup"><span data-stu-id="c7dcb-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="c7dcb-232">Модули верхнего уровня может содержать функции F # без необходимости внутренним</span><span class="sxs-lookup"><span data-stu-id="c7dcb-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="c7dcb-233">Выбор между пространством имен верхнего уровня или модуль влияет на форме скомпилированного кода и таким образом повлияет на представлении из других языков .NET следует API со временем использовать за пределами кода F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="c7dcb-234">Использовать методы и свойства для операций, характерными для типов объектов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="c7dcb-235">При работе с объектами, нужно убедиться, что готовых к использованию функциональность реализуется как методы и свойства этого типа.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="c7dcb-236">Не, основная часть функций для данного элемента должны обязательно будут реализованы в этот элемент, но должно быть готовых к использованию части эту функциональность.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="c7dcb-237">Использование классов, инкапсулирующих изменяемое состояние</span><span class="sxs-lookup"><span data-stu-id="c7dcb-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="c7dcb-238">В языке F # это достаточно сделать где что состояние не уже инкапсулируется другой языковой конструкции, такие как замыкание, выражения последовательности или асинхронное вычисление.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="c7dcb-239">Используйте интерфейсы для группирования операций, связанных с</span><span class="sxs-lookup"><span data-stu-id="c7dcb-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="c7dcb-240">Используйте типы интерфейсов для представления набора операций.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="c7dcb-241">Это предпочтительнее другие параметры, например кортежей, функций или записей функций.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="c7dcb-242">В ссылке к:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="c7dcb-243">Интерфейсы являются понятиями первостепенными в .NET, который можно использовать для достижения, что Функторы обычно отображаются.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="c7dcb-244">Кроме того они могут использоваться для кодирования типов уже существует в вашу программу, которой нет записей функций.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="c7dcb-245">Использование модуля группы функций, которые действуют в коллекциях</span><span class="sxs-lookup"><span data-stu-id="c7dcb-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="c7dcb-246">При определении типа коллекции, подберите стандартный набор операций, например `CollectionType.map` и `CollectionType.iter`) для новых типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="c7dcb-247">При включении таких модулей, следуйте стандартным соглашениям об именовании для функций, содержащихся в FSharp.Core.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="c7dcb-248">Использование модуля группы функций для общих канонических функций, особенно в math и библиотеки DSL</span><span class="sxs-lookup"><span data-stu-id="c7dcb-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="c7dcb-249">Например `Microsoft.FSharp.Core.Operators` — автоматического открытия коллекция функции верхнего уровня (например `abs` и `sin`), предоставляемые FSharp.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="c7dcb-250">Аналогичным образом, библиотека статистики может включать модуль с функциями `erf` и `erfc`, где этот модуль предназначен должны быть открыты автоматически.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="c7dcb-251">Рассмотрите возможность использования RequireQualifiedAccess и тщательно применять атрибуты AutoOpen</span><span class="sxs-lookup"><span data-stu-id="c7dcb-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="c7dcb-252">Добавление `[<RequireQualifiedAccess>]` атрибут к модулю указывает, что модуль не может быть открыт, и необходимость явной ссылки на элементы модуля полного доступа.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="c7dcb-253">Например `Microsoft.FSharp.Collections.List` модуля с этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="c7dcb-254">Это полезно в том случае, если функции и значения в модуле имеют имена, которые могут конфликтовать с именами в других модулях.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="c7dcb-255">Требуется метод доступа может значительно увеличивать долгосрочной поддержки и развиваемости библиотеки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="c7dcb-256">Добавление `[<AutoOpen>]` атрибут к модулю означает, что модуль будет открываться при открытии содержащего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="c7dcb-257">`[<AutoOpen>]` Атрибут также может быть применен к сборке, чтобы указать модуль, который автоматически открывается при ссылке на сборку.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="c7dcb-258">Например, библиотеку статистики **MathsHeaven.Statistics** может содержать `module MathsHeaven.Statistics.Operators` функции `erf` и `erfc`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="c7dcb-259">Следует отметить этот модуль как `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="c7dcb-260">Это означает, что `open MathsHeaven.Statistics` будет также открыть этот модуль и вывести имена `erf` и `erfc` в область действия.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="c7dcb-261">Использование другой good `[<AutoOpen>]` для модулей, содержащих методы расширения.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="c7dcb-262">Излишнее применение параметров `[<AutoOpen>]` приводит к его засорения пространств имен, а атрибуту следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="c7dcb-263">Для определенных библиотек в определенных доменах, разумно использовать `[<AutoOpen>]` может привести к более удобной.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="c7dcb-264">Рекомендуется определять оператор членов в классах, в которых подходит использование хорошо известного операторов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="c7dcb-265">Иногда классы используются для моделирования математической конструкции, такие как векторы.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="c7dcb-266">Если домен моделируемой содержит хорошо известных операторов, определяя их в качестве членов, встроенные в класс полезен.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="c7dcb-267">В этом руководстве соответствует общих рекомендаций .NET для этих типов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="c7dcb-268">Однако бывает, кроме того, важно в F # кодирования, так как он разрешает этих типов для использования в вместе с F #-функции и методы с ограничениями элементов, таких как List.sumBy.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="c7dcb-269">Рассмотрите возможность использования CompiledName для предоставления. NET-понятное имя для других потребителей язык .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="c7dcb-270">Иногда вы можете назвать в один стиль для потребителей F # (таких как статический член в нижнем регистре, чтобы он располагался как будто связанного с модулем функции), но имеют другой стиль для имени, при компиляции в сборку.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="c7dcb-271">Можно использовать `[<CompiledName>]` атрибут для предоставления другой стиль для использования сборки кода не F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="c7dcb-272">С помощью `[<CompiledName>]`, вы можете использовать соглашения об именовании .NET для пользователей не F # сборки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="c7dcb-273">Используйте перегрузки метода для функций-членов, если такой подход обеспечивает простой API</span><span class="sxs-lookup"><span data-stu-id="c7dcb-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="c7dcb-274">Перегрузка метода является мощным средством для упрощения API, который может потребоваться выполнить аналогичные функциональные возможности, но разные параметры и аргументы.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="c7dcb-275">В F # чаще для перегрузки на число аргументов, а не типы аргументов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="c7dcb-276">Скрыть представления типы объединений и записи, если разработка этих типов — вероятно эволюционирование</span><span class="sxs-lookup"><span data-stu-id="c7dcb-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="c7dcb-277">Избегайте раскрытия конкретные представления объектов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="c7dcb-278">Например, конкретные представление <xref:System.DateTime> значения не раскрываются внешних, открытый в API для разработки библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="c7dcb-279">Во время выполнения среда CLR знает зафиксированных реализации, который будет использоваться на протяжении выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="c7dcb-280">Тем не менее скомпилированный код не сам получают зависимостей от конкретного представления.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="c7dcb-281">Избегайте использования реализации наследования для расширяемости</span><span class="sxs-lookup"><span data-stu-id="c7dcb-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="c7dcb-282">В F # наследование реализации используется редко.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="c7dcb-283">Кроме того часто иерархий наследования являются сложными и трудно изменить, когда поступают новые требования.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="c7dcb-284">Реализация наследования по-прежнему существует в F # для совместимости и редких случаях, когда он является лучшим решением проблемы альтернативных методик, необходимо обратиться в программах F #, при разработке для полиморфизма, таких как реализация интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="c7dcb-285">Функция и элемент подписи</span><span class="sxs-lookup"><span data-stu-id="c7dcb-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="c7dcb-286">Использование кортежей для возвращаемых значений, при возврате небольшое количество несколько несвязанных значений</span><span class="sxs-lookup"><span data-stu-id="c7dcb-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="c7dcb-287">Вот хороший пример использования в возвращаемом типе кортежа:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="c7dcb-288">Для возврата типов, содержащих множество компонентов или там, где компоненты связаны с одной идентифицировать сущности, рассмотрите возможность использования именованного типа вместо кортежа.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="c7dcb-289">Используйте `Async<T>` для асинхронного программирования на границах API F #</span><span class="sxs-lookup"><span data-stu-id="c7dcb-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="c7dcb-290">Если имеется соответствующий синхронную операцию с именем `Operation` , возвращающий `T`, то асинхронная операция должна называться `AsyncOperation` при его использовании возвращается `Async<T>` или `OperationAsync` при его использовании возвращается `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="c7dcb-291">Для часто используемых типов .NET, которые предоставляют методов Begin и End, рассмотрите возможность использования `Async.FromBeginEnd` для записи методы расширения в качестве оболочки для предоставления F # асинхронную модель программирования этих интерфейсов API .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="c7dcb-292">Исключения</span><span class="sxs-lookup"><span data-stu-id="c7dcb-292">Exceptions</span></span>

<span data-ttu-id="c7dcb-293">См. в разделе [управление обработкой ошибок](conventions.md#error-management) Дополнительные сведения о соответствующее использование исключений, результаты и параметры.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-293">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="c7dcb-294">Члены расширений</span><span class="sxs-lookup"><span data-stu-id="c7dcb-294">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="c7dcb-295">Тщательно применить F # члены расширений для в F #-к-компонентов F #</span><span class="sxs-lookup"><span data-stu-id="c7dcb-295">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="c7dcb-296">Члены расширений F #, обычно только используется в для операций, которые находятся в закрытии внутренних операций, связанных с типом в большинстве режимов, его использования.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-296">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="c7dcb-297">Один обычно используется для предоставления API, которые являются более устойчивым к F # для различных типов .NET:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-297">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="c7dcb-298">Типы объединений</span><span class="sxs-lookup"><span data-stu-id="c7dcb-298">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="c7dcb-299">Использование размеченных объединений вместо иерархий классов для древовидной данных</span><span class="sxs-lookup"><span data-stu-id="c7dcb-299">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="c7dcb-300">Древовидной структуры являются рекурсивного определения.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-300">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="c7dcb-301">Это неудобно с наследованием, но элегантного с размеченные объединения.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-301">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="c7dcb-302">Представления данных дерева с размеченные объединения также позволяет использовать преимущества exhaustiveness при сопоставлении шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-302">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="c7dcb-303">Используйте `[<RequireQualifiedAccess>]` на типы объединения вариантов, имена которых не являются достаточно уникальными</span><span class="sxs-lookup"><span data-stu-id="c7dcb-303">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="c7dcb-304">Вы обнаружите себя в домене, где имя рекомендации для выполнения различных задач, таких как случаи размеченного объединения тем же именем.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-304">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="c7dcb-305">Можно использовать `[<RequireQualifiedAccess>]` для однозначного определения вариантов имена во избежание активации заблуждение ошибок из-за затенение зависит от порядка `open` инструкций</span><span class="sxs-lookup"><span data-stu-id="c7dcb-305">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="c7dcb-306">Скрыть представления размеченные объединения для двоичных совместимых API, если разработка этих типов — вероятно эволюционирование</span><span class="sxs-lookup"><span data-stu-id="c7dcb-306">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="c7dcb-307">Типы объединений, зависят от F # поиска совпадения с шаблоном формы для краткости модель программирования.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-307">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="c7dcb-308">Как упоминалось ранее, следует избегать раскрытия представления конкретных данных, если разработка этих типов — вероятно эволюционирование.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-308">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="c7dcb-309">Например, представление размеченное объединение можно скрыть с помощью объявление закрытого или внутреннего или с помощью подписи файла.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-309">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="c7dcb-310">Если вы раскрываете информацию размеченные объединения беспорядочно, может оказаться трудно версии библиотеки без нарушения кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-310">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="c7dcb-311">Вместо этого рассмотрите возможность раскрытия один или несколько активных шаблонов, позволяющая сопоставления над значениями типа шаблона.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-311">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="c7dcb-312">Активные шаблоны предоставляют альтернативный способ предоставить потребителям F # сопоставления избегая предоставление типов объединения F # напрямую шаблона.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-312">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="c7dcb-313">Встроенные функции и ограничения члена</span><span class="sxs-lookup"><span data-stu-id="c7dcb-313">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="c7dcb-314">Определите универсальный числовые алгоритмы, с помощью встроенных функций с ограничениями подразумеваемых членов и статически разрешаемым универсальные типы</span><span class="sxs-lookup"><span data-stu-id="c7dcb-314">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="c7dcb-315">Арифметические член ограничения и ограничения сравнения F # являются стандартом для программирование на F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-315">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="c7dcb-316">Рассмотрим следующий пример кода:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-316">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="c7dcb-317">Тип этой функции выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-317">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="c7dcb-318">Это подходящая функция для общего API в математической библиотеки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-318">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="c7dcb-319">Старайтесь не использовать член ограничения для имитации классов типа и типизации по признакам</span><span class="sxs-lookup"><span data-stu-id="c7dcb-319">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="c7dcb-320">Можно имитировать «типизации по признакам» с помощью ограничений члена F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-320">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="c7dcb-321">Однако члены, которые делают с помощью этого следует использовать не в общие в F #-к-проекты библиотеки F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-321">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="c7dcb-322">Это обусловлено тем, как правило, вызвать пользовательский код стать неудобными и привязаны к одной конкретной платформой шаблон библиотеки макетов на основе незнакомых или нестандартные неявное ограничений.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-322">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="c7dcb-323">Кроме того есть шанс, что активно использовать ограничения член таким образом может привести компиляции очень много времени.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-323">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="c7dcb-324">Оператор определения</span><span class="sxs-lookup"><span data-stu-id="c7dcb-324">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="c7dcb-325">Не рекомендуется определять пользовательские операторы, символьные</span><span class="sxs-lookup"><span data-stu-id="c7dcb-325">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="c7dcb-326">Пользовательские операторы необходимы в некоторых случаях и очень удобен в обозначениям устройства в больших частях кода реализации.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-326">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="c7dcb-327">Для новых пользователей библиотеки именованных функций зачастую проще в использовании.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-327">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="c7dcb-328">Кроме того пользовательские символьные операторы могут возникнуть трудности с документов и пользователям будет сложно более поиск справки по операторам, из-за ограничений существующих обработчиков интегрированной среды разработки и поиска.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-328">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="c7dcb-329">Таким образом рекомендуется для публикации в виде именованных функций и члены и Кроме того, только в том случае, если значимых преимуществ перевешивают документация и cognitive затраты на их, предоставлять операторы для использования этой функции.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-329">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="c7dcb-330">Единицы измерения</span><span class="sxs-lookup"><span data-stu-id="c7dcb-330">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="c7dcb-331">Тщательно единицы измерения используются в целях безопасности добавлен тип в коде F #</span><span class="sxs-lookup"><span data-stu-id="c7dcb-331">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="c7dcb-332">Дополнительные сведения о типизации для единицы измерения удаляется при его просмотре на других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-332">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="c7dcb-333">Имейте в виду, что компоненты .NET и средства отражения будут видеть типы sans единиц.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-333">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="c7dcb-334">Например, C# пользователи увидят `float` вместо `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-334">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="c7dcb-335">Сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-335">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="c7dcb-336">Внимательно используйте сокращенные формы типов для упрощения кода на F #</span><span class="sxs-lookup"><span data-stu-id="c7dcb-336">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="c7dcb-337">Компоненты .NET и средства отражения не увидит сокращенные имена для типов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-337">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="c7dcb-338">Значительное использование сокращенные формы типов также можно сделать домена отображаются более сложным, чем он фактически является, которой удалось вводят в заблуждение потребителей.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-338">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="c7dcb-339">Избегайте сокращенные формы типов для открытых типов, членов и свойств должны отличаться по своей природе для тех, которые доступны для типа сокращается</span><span class="sxs-lookup"><span data-stu-id="c7dcb-339">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="c7dcb-340">В этом случае тип сокращается показывает, что слишком многое о представлении фактический тип определяемого.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-340">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="c7dcb-341">Вместо этого рассмотрите возможность упаковки аббревиатура в тип класса или одиночным размеченного объединения (или, если важна производительность, рассмотрите возможность использования типа структуры программы-оболочки для сокращения).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-341">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="c7dcb-342">Например это подмывает вас определить карту несколькими как особый случай F # карты, например:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-342">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="c7dcb-343">Тем не менее операции логического нотацию для этого типа не так же, как операции на карте — например, разумно, оператор поиска были сопоставлены. [key] Возврат пустой список, если ключа нет в словаре, а не вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-343">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="c7dcb-344">Рекомендации для библиотек для использования из других языков .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-344">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="c7dcb-345">При разработке библиотек для использования в других языках .NET, очень важно придерживаться [рекомендации по разработке библиотек .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-345">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="c7dcb-346">В этом документе, эти библиотеки помечены как стандартный библиотеки .NET, в отличие от F #-с выходом библиотеки, использующие F # создает без ограничений.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-346">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="c7dcb-347">Проектирование vanilla библиотек .NET означает, предоставляя знакомые и устойчивым API согласования с остальной частью платформы .NET Framework, сводя к минимуму использование F #-конкретных конструкций в открытом API.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-347">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="c7dcb-348">В следующих разделах описаны правила.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-348">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="c7dcb-349">Пространство имен и тип конструктора (для библиотек для использования из других языков .NET)</span><span class="sxs-lookup"><span data-stu-id="c7dcb-349">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="c7dcb-350">Применить соглашения об именовании .NET для открытого API-интерфейса компонентов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-350">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="c7dcb-351">Обратите внимание на использование сокращенные имена и регистр букв рекомендациям .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-351">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="c7dcb-352">Используйте пространства имен, типы и члены как основной организационной структурой для компонентов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-352">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="c7dcb-353">Все файлы, содержащие открытые методы должны начинаться с `namespace` объявления и только общедоступные сущности в пространствах имен, которые должны быть типы.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-353">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="c7dcb-354">Не используйте модули F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-354">Do not use F# modules.</span></span>

<span data-ttu-id="c7dcb-355">Используйте модули не являющиеся открытыми для размещения код реализации, служебные типы и служебных функций.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-355">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="c7dcb-356">Статические типы лучше использовать модули, так как позволяют использовать перегрузки и другие принципы проектирования .NET API, которые не могут использоваться в модулях, F # для будущего развития API.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-356">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="c7dcb-357">Например, вместо следующих открытого API-интерфейса:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-357">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="c7dcb-358">Попробуйте вместо этого:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-358">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="c7dcb-359">Используйте типов записи на F # в ваниль API-интерфейсы .NET, если не будет развиваться разработки типов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-359">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="c7dcb-360">Типы записей F # компилируются в простой класс .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-360">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="c7dcb-361">Они подходят для некоторых типов простых и стабильных в API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-361">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="c7dcb-362">Следует рассмотреть возможность использования `[<NoEquality>]` и `[<NoComparison>]` атрибуты, чтобы отключить автоматическое создание интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-362">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="c7dcb-363">Также Избегайте поля изменяемых записей в обычный API-интерфейсы .NET как эти предоставляет открытое поле.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-363">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="c7dcb-364">Всегда учитывайте, будет ли класс предоставляет более гибкий вариант для будущего развития API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-364">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="c7dcb-365">Например следующий код на F # предоставляет открытый API для потребителя C#:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-365">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="c7dcb-366">F #:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-366">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="c7dcb-367">C#:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-367">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="c7dcb-368">Скрыть представление типов F # объединения в обычный API-интерфейсы .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-368">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="c7dcb-369">Типы объединений F # не распространены через границы компонентов, даже для F #-к-F # кодирования.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-369">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="c7dcb-370">Это устройство отличную реализации при для внутреннего использования в компоненты и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-370">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="c7dcb-371">При разработке обычный .NET API, можно скрыть представление типа объединения, используя объявление закрытого или файл сигнатур.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-371">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="c7dcb-372">Кроме того, может быть расширено типов, которые внутренне используют представление union с членами для обеспечения требуемой. NET API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-372">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="c7dcb-373">Проектирование графического пользовательского интерфейса и другими компонентами с помощью шаблонов разработки платформы</span><span class="sxs-lookup"><span data-stu-id="c7dcb-373">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="c7dcb-374">Существует множество различных платформ в .NET, например WinForms, WPF и ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-374">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="c7dcb-375">Соглашения об именовании и проектирования для каждого можно использовать при разработке компонентов, используемых в этих платформ.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-375">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="c7dcb-376">Например для программирования WPF, внедряйте WPF шаблоны разработки для классов, которые вы разрабатываете.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-376">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="c7dcb-377">Для моделей в программировании пользовательского интерфейса, используйте шаблоны проектирования, таких как события и коллекций на основе уведомлений, например из статьи <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-377">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="c7dcb-378">Объекты и элементы проектирования (для библиотек для использования из других языков .NET)</span><span class="sxs-lookup"><span data-stu-id="c7dcb-378">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="c7dcb-379">Используется для предоставления событий .NET CLIEvent-атрибут</span><span class="sxs-lookup"><span data-stu-id="c7dcb-379">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="c7dcb-380">Создать `DelegateEvent` с определенной .NET делегат типа, который принимает объект и `EventArgs` (вместо `Event`, которой пользуется только `FSharpHandler` тип по умолчанию) таким образом, чтобы события, публикуются в знакомый способ других языков .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-380">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="c7dcb-381">Предоставлять асинхронные операции, как методы, которые возвращают задачи .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-381">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="c7dcb-382">Задачи используются в .NET для представления active асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-382">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="c7dcb-383">Задачи, в целом, менее композиционной, чем F # `Async<T>` объектов, так как они представляют задачи «уже выполняется» и не может содержать вместе одним из способов, которые выполняют параллельные композиции или который скрыть распространение сигналы отмены и других контекстные параметры.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-383">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="c7dcb-384">Однако несмотря на это, методы, которые возвращают задачи, стандартное представление асинхронного программирования на платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-384">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="c7dcb-385">Вы будете часто Обраб явного токена отмены:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-385">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="c7dcb-386">Использование типов делегатов .NET вместо типов функция F #</span><span class="sxs-lookup"><span data-stu-id="c7dcb-386">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="c7dcb-387">Здесь «типы функция F #» означает «стрелка» типов, таких как `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-387">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="c7dcb-388">Вместо этого:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-388">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="c7dcb-389">Выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-389">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="c7dcb-390">Тип функции F # отображается как `class FSharpFunc<T,U>` на других языках .NET и этот процесс менее подходит для функций языка и инструменты, которые понимают типы делегатов.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-390">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="c7dcb-391">При создании метода более высокого порядка, предназначенных для .NET Framework 3.5 или более поздней версии, `System.Func` и `System.Action` делегаты являются правой API-интерфейсы для публикации позволяет разработчикам .NET использовать эти API-интерфейсы в виде низким коэффициентом трения.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-391">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="c7dcb-392">(При нацеливании на .NET Framework 2.0, типы делегатов, определяемые системой более ограничены; рассмотрите возможность использования делегата предопределенные типы, такие как `System.Converter<T,U>` или определение определенному типу делегата.)</span><span class="sxs-lookup"><span data-stu-id="c7dcb-392">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="c7dcb-393">С другой стороны, делегаты .NET не являются естественным для языка F #-с выходом библиотек (в следующем разделе на F #-с выходом библиотек).</span><span class="sxs-lookup"><span data-stu-id="c7dcb-393">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="c7dcb-394">Таким образом распространенные стратегия реализации при разработке методы более высокого порядка для соответствующего ванили библиотек .NET — создание всех реализации, с помощью функции типов F #, а затем создать открытый интерфейс API с использованием делегатов в качестве тонкой оболочки поверх фактическое F # Реализация.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-394">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="c7dcb-395">Использование шаблона TryGetValue вместо возвращения значения параметров F # и предпочитаете перегрузка методов с созданием параметр значения F # в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="c7dcb-395">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="c7dcb-396">Общие шаблоны использования для типа параметра F # в API-интерфейсы работают лучше реализации в ваниль методы разработки API-интерфейсы .NET, с помощью standard .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-396">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="c7dcb-397">Вместо возвращения значения параметра F #, рассмотрите возможность использования возвращаемый тип bool, а также как в шаблоне «TryGetValue» выходной параметр.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-397">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="c7dcb-398">И вместо значения параметров F # в качестве параметров, рассмотрите возможность использования перегрузки метода или необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-398">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="c7dcb-399">Использовать интерфейс коллекции .NET типы IEnumerable\<T\> и IDictionary\<ключ, значение\> для параметров и возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="c7dcb-399">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="c7dcb-400">Не рекомендуется использовать конкретный набор типов, таких как массивы .NET `T[]`, типы F # `list<T>`, `Map<Key,Value>` и `Set<T>`, и .NET конкретные типы коллекций, такие как `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-400">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="c7dcb-401">Рекомендации по разработке библиотек .NET имеют хороший совет, касающийся необходимости использования различных типов коллекций, такие как `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-401">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="c7dcb-402">Некоторые использование массивов (`T[]`) допустима в некоторых случаях на территории производительности.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-402">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="c7dcb-403">Обратите внимание, особенно что `seq<T>` является просто F # псевдоним для `IEnumerable<T>`, и поэтому seq часто соответствующих типов для обычный .NET API.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-403">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="c7dcb-404">Вместо списков F #:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-404">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="c7dcb-405">Использование последовательностей F #:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-405">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="c7dcb-406">Используйте тип единицы измерения как единственный входной тип метода для определения метода нулевой аргумент, или как единственный возвращаемый тип для определения метода, возвращающего значение void</span><span class="sxs-lookup"><span data-stu-id="c7dcb-406">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="c7dcb-407">Избегайте других вариантов использования тип единицы измерения.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-407">Avoid other uses of the unit type.</span></span> <span data-ttu-id="c7dcb-408">Это хороший:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-408">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="c7dcb-409">Это неправильный:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-409">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="c7dcb-410">Проверять наличие значений null по границам стандартный API для .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-410">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="c7dcb-411">Реализация кода F # обычно имеют меньшее количество значений null, из-за неизменяемый конструктивные шаблоны и ограничения использования литералы null для типов F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-411">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="c7dcb-412">Другими языками .NET часто используют значение null гораздо чаще.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-412">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="c7dcb-413">По этой причине код F #, которая предоставляет обычный .NET API следует проверять параметры со значением NULL на границе API и предотвратить эти значения поступают глубже в код реализации F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-413">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="c7dcb-414">`isNull` Функции или шаблоны на `null` шаблон может использоваться.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-414">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="c7dcb-415">Старайтесь не использовать кортежи как возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="c7dcb-415">Avoid using tuples as return values</span></span>

<span data-ttu-id="c7dcb-416">Вместо этого предпочитают, возвращая именованный тип, содержащий статистические данные, или использование выходных параметров для возврата нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-416">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="c7dcb-417">Несмотря на то, что кортежи и кортежи, структура существует в .NET (в том числе поддержка языка C# для структурных кортежей), они чаще всего не будет предоставлять идеальная и ожидаемый интерфейс API для разработчиков .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-417">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="c7dcb-418">Избегайте использования каррирование параметров</span><span class="sxs-lookup"><span data-stu-id="c7dcb-418">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="c7dcb-419">Вместо этого использовать соглашения о вызовах .NET ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-419">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="c7dcb-420">Совет: При создании библиотек для использования в любом языке .NET, то нет никакой альтернативы делать некоторые экспериментальные C# и Visual Basic программирования, чтобы убедиться, что библиотеки «вид справа» из этих языков.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-420">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="c7dcb-421">Средства, такие как .NET Reflector и обозревателя объектов Visual Studio также можно гарантией библиотек и связанную документацию для разработчиков должным образом.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-421">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="c7dcb-422">Приложение</span><span class="sxs-lookup"><span data-stu-id="c7dcb-422">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="c7dcb-423">End-to-end пример создания кода F # для использования с другими языками .NET</span><span class="sxs-lookup"><span data-stu-id="c7dcb-423">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="c7dcb-424">Рассмотрим следующий класс:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-424">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="c7dcb-425">Выведенный тип F # этот класс выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-425">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="c7dcb-426">Давайте рассмотрим, как выглядит этот тип F # программисту, используя другой язык .NET.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-426">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="c7dcb-427">Например приблизительное C# «подпись» выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-427">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="c7dcb-428">Существуют некоторые важные особенности о том, как F # представляет конструкции здесь.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-428">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="c7dcb-429">Пример:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-429">For example:</span></span>

* <span data-ttu-id="c7dcb-430">Метаданные, такие как имена аргументов был сохранен.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-430">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="c7dcb-431">F # методы, которые принимают два аргумента становятся методы C#, которые принимают два аргумента.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-431">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="c7dcb-432">Функции и списки становятся ссылки на соответствующие типы в библиотеке F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-432">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="c7dcb-433">Ниже показано, как настроить этот код необходимо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-433">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="c7dcb-434">Выведенный тип F # код выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-434">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="c7dcb-435">Сигнатура C# — теперь следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-435">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="c7dcb-436">Внесены исправления для подготовки к использованию этого типа, как часть стандартного библиотеки .NET являются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c7dcb-436">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="c7dcb-437">Изменить несколько имен: `Point1`, `n`, `l`, и `f` стали `RadialPoint`, `count`, `factor`, и `transform`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-437">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="c7dcb-438">Используемый тип возвращаемого значения `seq<RadialPoint>` вместо `RadialPoint list` путем изменения конструкции списка с помощью `[ ... ]` для создания последовательности с помощью `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-438">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="c7dcb-439">Используемый тип делегата .NET `System.Func` вместо типа функции F #.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-439">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="c7dcb-440">Это делает гораздо лучше, для использования в коде C#.</span><span class="sxs-lookup"><span data-stu-id="c7dcb-440">This makes it far nicer to consume in C# code.</span></span>
