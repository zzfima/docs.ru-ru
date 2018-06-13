---
title: 'Рекомендации по проектированию компонент F #'
description: 'Дополнительные рекомендации по написанию компонентов F #, предназначен для использования в других вызывающих объектов.'
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458090"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="f4902-103">Рекомендации по проектированию компонент F #</span><span class="sxs-lookup"><span data-stu-id="f4902-103">F# component design guidelines</span></span>

<span data-ttu-id="f4902-104">Этот документ представляет собой набор компонентов правилам разработки для языка F # программирования, в зависимости от F # компонент рекомендации по разработке, v14, Microsoft Research и [другая версия](https://fsharp.org/specs/component-design-guidelines/) изначально курируемый и обслуживается Software Foundation F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="f4902-105">В этом документе предполагается, что вы знакомы с программированием на языке F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="f4902-106">Выражаем благодарность сообщества F # для их вклад и полезные отзывы в разных версиях данного руководства.</span><span class="sxs-lookup"><span data-stu-id="f4902-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="f4902-107">Обзор</span><span class="sxs-lookup"><span data-stu-id="f4902-107">Overview</span></span>

<span data-ttu-id="f4902-108">В этом документе рассматриваются некоторые вопросы, связанные с F # компонент проектирование и кодирование.</span><span class="sxs-lookup"><span data-stu-id="f4902-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="f4902-109">Компонент может иметь одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="f4902-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="f4902-110">Слой в проекте F #, имеющий внешних потребителей в рамках проекта.</span><span class="sxs-lookup"><span data-stu-id="f4902-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="f4902-111">Библиотека предназначена для использования в коде F # за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="f4902-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="f4902-112">Библиотека, предназначен для использования в любом языке .NET за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="f4902-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="f4902-113">Библиотека, предназначенных для распространения через репозитория пакетов, таких как [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="f4902-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="f4902-114">Выполните указания, приведенные в этой статье [пять принципов хороший код F #](index.md#five-principles-of-good-f-code)и таким образом использовать оба функционального и объекта программирования соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="f4902-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="f4902-115">Независимо от того, методику конструктор компонентов и библиотека сталкивается с различными практичный и прозаическом проблемы при попытке создать интерфейс API, проще всего использовать разработчиками.</span><span class="sxs-lookup"><span data-stu-id="f4902-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="f4902-116">Применение conscientious [правилам разработки библиотеки .NET](../../standard/design-guidelines/index.md) будет управлять процессом по созданию согласованного набора интерфейсов API, удобную для использования.</span><span class="sxs-lookup"><span data-stu-id="f4902-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="f4902-117">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="f4902-117">General guidelines</span></span>

<span data-ttu-id="f4902-118">Существует несколько универсальных правил, применимых к библиотеки F #, независимо от того, целевая аудитория для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f4902-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="f4902-119">Дополнительные сведения согласно правилам разработки библиотеки .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="f4902-120">Независимо от типа F # кодирования, вы выполняете, важно иметь опыт работы с [правилам разработки библиотеки .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4902-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="f4902-121">Большинство других F # и .NET программистам будет иметь навыки работы с помощью этих рекомендаций; ожидается код .NET, чтобы соответствовать им.</span><span class="sxs-lookup"><span data-stu-id="f4902-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="f4902-122">Согласно правилам разработки библиотеки .NET обеспечивает общие рекомендации относительно именования, конструирование классов и интерфейсов, член конструктора (свойства, методы, события, т. д.) и более и полезные первой точки ссылки для разнообразных руководство по проектированию.</span><span class="sxs-lookup"><span data-stu-id="f4902-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="f4902-123">Добавьте в код комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="f4902-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="f4902-124">XML-документации на общедоступных API убедитесь, что пользователи могут получить значительные Intellisense и краткие сведения с помощью этих типов и членов и включить создание документации файлов для библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f4902-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="f4902-125">В разделе [XML-документации](../language-reference/xml-documentation.md) о различных XML-теги, которые могут использоваться для дополнительных разметка в рамках xmldoc комментарии.</span><span class="sxs-lookup"><span data-stu-id="f4902-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

<span data-ttu-id="f4902-126">Можно использовать комментарии XML краткая форма (`/// comment`), или стандартные XML-комментарии (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="f4902-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="f4902-127">Рассмотрите возможность использования явное подписи файлов (.fsi) для stable библиотеки и API-интерфейсы компонента</span><span class="sxs-lookup"><span data-stu-id="f4902-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="f4902-128">С помощью явных подписи файлов в библиотеке F # Сводка сжатой открытый API, для которых позволяет гарантировать, что вы знаете полного открытого рабочей области библиотеки, а также обеспечивает четкое разделение между документации открытых и внутренних сведения о реализации.</span><span class="sxs-lookup"><span data-stu-id="f4902-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="f4902-129">Обратите внимание, что файлы сигнатур добавить трения изменение открытого API-интерфейса, при необходимости вносить изменения в реализации и подписи файлов.</span><span class="sxs-lookup"><span data-stu-id="f4902-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="f4902-130">В результате файлы сигнатур должен обычно только быть привело к появлению API становятся упрочило и больше не может значительно измениться.</span><span class="sxs-lookup"><span data-stu-id="f4902-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="f4902-131">Всегда Следуйте советам и рекомендациям по использованию строк в .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="f4902-132">Выполните [советы и рекомендации по использованию строк в .NET](../../standard/base-types/best-practices-strings.md) рекомендации.</span><span class="sxs-lookup"><span data-stu-id="f4902-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="f4902-133">В частности, всегда явно указывать *региональные намерение* преобразования и сравнение строк (где применимо).</span><span class="sxs-lookup"><span data-stu-id="f4902-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="f4902-134">Рекомендации для языка F # — с выходом библиотеки</span><span class="sxs-lookup"><span data-stu-id="f4902-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="f4902-135">В этом разделе даются рекомендации по разработке открытый F # — с выходом библиотеки; то есть, библиотек, предоставление открытые API, которые предназначены для использования разработчиками F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="f4902-136">Специально для языка F # применяются различные рекомендации по проектированию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f4902-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="f4902-137">В случае отсутствия конкретные рекомендации, которые выполните согласно правилам разработки библиотеки .NET — это резервная рекомендации.</span><span class="sxs-lookup"><span data-stu-id="f4902-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="f4902-138">Соглашения об именах</span><span class="sxs-lookup"><span data-stu-id="f4902-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="f4902-139">Используйте соглашения об именовании и регистр букв .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="f4902-140">Соглашения об именовании и регистр букв .NET учтена в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f4902-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="f4902-141">Существуют небольшие дополнения для включения конструкции в F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="f4902-142">Конструкция</span><span class="sxs-lookup"><span data-stu-id="f4902-142">Construct</span></span> | <span data-ttu-id="f4902-143">Case</span><span class="sxs-lookup"><span data-stu-id="f4902-143">Case</span></span> | <span data-ttu-id="f4902-144">Отделение</span><span class="sxs-lookup"><span data-stu-id="f4902-144">Part</span></span> | <span data-ttu-id="f4902-145">Примеры</span><span class="sxs-lookup"><span data-stu-id="f4902-145">Examples</span></span> | <span data-ttu-id="f4902-146">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4902-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="f4902-147">Конкретные типы</span><span class="sxs-lookup"><span data-stu-id="f4902-147">Concrete types</span></span> | <span data-ttu-id="f4902-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-148">PascalCase</span></span> | <span data-ttu-id="f4902-149">Существительное / прилагательных</span><span class="sxs-lookup"><span data-stu-id="f4902-149">Noun/ adjective</span></span> | <span data-ttu-id="f4902-150">Список, Double, сложный</span><span class="sxs-lookup"><span data-stu-id="f4902-150">List, Double, Complex</span></span> | <span data-ttu-id="f4902-151">Конкретные типы являются структуры, классы, перечисления, делегаты, записей и объединений.</span><span class="sxs-lookup"><span data-stu-id="f4902-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="f4902-152">Хотя в большинстве случаев нижнего регистра в OCaml имена типов F # приняла схему именования .NET для типов.</span><span class="sxs-lookup"><span data-stu-id="f4902-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="f4902-153">библиотеки DLL</span><span class="sxs-lookup"><span data-stu-id="f4902-153">DLLs</span></span>           | <span data-ttu-id="f4902-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-154">PascalCase</span></span> |                 | <span data-ttu-id="f4902-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="f4902-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="f4902-156">Объединить теги</span><span class="sxs-lookup"><span data-stu-id="f4902-156">Union tags</span></span>     | <span data-ttu-id="f4902-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-157">PascalCase</span></span> | <span data-ttu-id="f4902-158">существительное</span><span class="sxs-lookup"><span data-stu-id="f4902-158">Noun</span></span> | <span data-ttu-id="f4902-159">Некоторые из них, добавлять, успех</span><span class="sxs-lookup"><span data-stu-id="f4902-159">Some, Add, Success</span></span> | <span data-ttu-id="f4902-160">Не используйте префикс в открытых интерфейсах API.</span><span class="sxs-lookup"><span data-stu-id="f4902-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="f4902-161">При необходимости использовать префикс, когда внутреннее, такие как "" тип команды = TAlpha</span><span class="sxs-lookup"><span data-stu-id="f4902-161">Optionally use a prefix when internal, such as \`\`\`type Teams = TAlpha</span></span> | <span data-ttu-id="f4902-162">TBeta</span><span class="sxs-lookup"><span data-stu-id="f4902-162">TBeta</span></span> | <span data-ttu-id="f4902-163">TDelta.'' "</span><span class="sxs-lookup"><span data-stu-id="f4902-163">TDelta.\`\`\`</span></span> |
| <span data-ttu-id="f4902-164">событие</span><span class="sxs-lookup"><span data-stu-id="f4902-164">Event</span></span>          | <span data-ttu-id="f4902-165">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-165">PascalCase</span></span> | <span data-ttu-id="f4902-166">Команда</span><span class="sxs-lookup"><span data-stu-id="f4902-166">Verb</span></span> | <span data-ttu-id="f4902-167">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="f4902-167">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="f4902-168">Исключения</span><span class="sxs-lookup"><span data-stu-id="f4902-168">Exceptions</span></span>     | <span data-ttu-id="f4902-169">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-169">PascalCase</span></span> |      | <span data-ttu-id="f4902-170">WebException</span><span class="sxs-lookup"><span data-stu-id="f4902-170">WebException</span></span> | <span data-ttu-id="f4902-171">Имя должно заканчиваться «Исключение».</span><span class="sxs-lookup"><span data-stu-id="f4902-171">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="f4902-172">Поле</span><span class="sxs-lookup"><span data-stu-id="f4902-172">Field</span></span>          | <span data-ttu-id="f4902-173">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-173">PascalCase</span></span> | <span data-ttu-id="f4902-174">существительное</span><span class="sxs-lookup"><span data-stu-id="f4902-174">Noun</span></span> | <span data-ttu-id="f4902-175">CurrentName</span><span class="sxs-lookup"><span data-stu-id="f4902-175">CurrentName</span></span>  | |
| <span data-ttu-id="f4902-176">Типы интерфейса</span><span class="sxs-lookup"><span data-stu-id="f4902-176">Interface types</span></span> |  <span data-ttu-id="f4902-177">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-177">PascalCase</span></span> | <span data-ttu-id="f4902-178">Существительное / прилагательных</span><span class="sxs-lookup"><span data-stu-id="f4902-178">Noun/ adjective</span></span> | <span data-ttu-id="f4902-179">IDisposable</span><span class="sxs-lookup"><span data-stu-id="f4902-179">IDisposable</span></span> | <span data-ttu-id="f4902-180">Имя должно начинаться с «I».</span><span class="sxs-lookup"><span data-stu-id="f4902-180">Name should start with “I”.</span></span> |
| <span data-ttu-id="f4902-181">Метод</span><span class="sxs-lookup"><span data-stu-id="f4902-181">Method</span></span> |  <span data-ttu-id="f4902-182">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-182">PascalCase</span></span> |  <span data-ttu-id="f4902-183">Команда</span><span class="sxs-lookup"><span data-stu-id="f4902-183">Verb</span></span> | <span data-ttu-id="f4902-184">ToString</span><span class="sxs-lookup"><span data-stu-id="f4902-184">ToString</span></span> | |
| <span data-ttu-id="f4902-185">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f4902-185">Namespace</span></span> | <span data-ttu-id="f4902-186">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-186">PascalCase</span></span> | | <span data-ttu-id="f4902-187">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="f4902-187">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="f4902-188">Как правило, использовать `<Organization>.<Technology>[.<Subnamespace>]`, но удалить организации, если технология не зависит от организации.</span><span class="sxs-lookup"><span data-stu-id="f4902-188">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="f4902-189">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4902-189">Parameters</span></span> | <span data-ttu-id="f4902-190">camelCase</span><span class="sxs-lookup"><span data-stu-id="f4902-190">camelCase</span></span> | <span data-ttu-id="f4902-191">существительное</span><span class="sxs-lookup"><span data-stu-id="f4902-191">Noun</span></span> |  <span data-ttu-id="f4902-192">Имя типа, преобразование, диапазон</span><span class="sxs-lookup"><span data-stu-id="f4902-192">typeName, transform, range</span></span> | |
| <span data-ttu-id="f4902-193">Разрешить значения (внутренний)</span><span class="sxs-lookup"><span data-stu-id="f4902-193">let values (internal)</span></span> | <span data-ttu-id="f4902-194">camelCase или PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-194">camelCase or PascalCase</span></span> | <span data-ttu-id="f4902-195">Существительное-команда</span><span class="sxs-lookup"><span data-stu-id="f4902-195">Noun/ verb</span></span> |  <span data-ttu-id="f4902-196">getValue myTable</span><span class="sxs-lookup"><span data-stu-id="f4902-196">getValue, myTable</span></span> |
| <span data-ttu-id="f4902-197">Разрешить значения (внешний)</span><span class="sxs-lookup"><span data-stu-id="f4902-197">let values (external)</span></span> | <span data-ttu-id="f4902-198">camelCase или PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-198">camelCase or PascalCase</span></span> | <span data-ttu-id="f4902-199">Существительное команда</span><span class="sxs-lookup"><span data-stu-id="f4902-199">Noun/verb</span></span>  | <span data-ttu-id="f4902-200">List.map Dates.Today</span><span class="sxs-lookup"><span data-stu-id="f4902-200">List.map, Dates.Today</span></span> | <span data-ttu-id="f4902-201">привязки let значения часто являются открытыми, при попытке шаблоны традиционных функциональной разработки.</span><span class="sxs-lookup"><span data-stu-id="f4902-201">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="f4902-202">Однако обычно используется PascalCase, если идентификатор может использоваться в других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-202">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="f4902-203">Свойство.</span><span class="sxs-lookup"><span data-stu-id="f4902-203">Property</span></span>  | <span data-ttu-id="f4902-204">PascalCase</span><span class="sxs-lookup"><span data-stu-id="f4902-204">PascalCase</span></span>  | <span data-ttu-id="f4902-205">Существительное / прилагательных</span><span class="sxs-lookup"><span data-stu-id="f4902-205">Noun/ adjective</span></span>  | <span data-ttu-id="f4902-206">IsEndOfFile BackColor</span><span class="sxs-lookup"><span data-stu-id="f4902-206">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="f4902-207">Логические свойства обычно использование является и могут и должны быть голосами как IsEndOfFile не IsNotEndOfFile.</span><span class="sxs-lookup"><span data-stu-id="f4902-207">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="f4902-208">Избегать сокращений</span><span class="sxs-lookup"><span data-stu-id="f4902-208">Avoid abbreviations</span></span>

<span data-ttu-id="f4902-209">Рекомендации по .NET отказа от использования сокращений (например, «использовать `OnButtonClick` вместо `OnBtnClick`»).</span><span class="sxs-lookup"><span data-stu-id="f4902-209">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="f4902-210">Сокращений, таких как `Async` для «Асинхронной», которая допустима.</span><span class="sxs-lookup"><span data-stu-id="f4902-210">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="f4902-211">Иногда это правило игнорируется для функционального программирования; например `List.iter` использует это сокращение для «итерация».</span><span class="sxs-lookup"><span data-stu-id="f4902-211">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="f4902-212">По этой причине использования сокращений, как правило, допустимое в большей степени в языке F #-к-программирование на F #, но по-прежнему обычно следует избегать в проектирования общих компонентов.</span><span class="sxs-lookup"><span data-stu-id="f4902-212">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="f4902-213">Избежать конфликтов имен регистр</span><span class="sxs-lookup"><span data-stu-id="f4902-213">Avoid casing name collisions</span></span>

<span data-ttu-id="f4902-214">Рекомендации по .NET говорят, что регистр отдельно не может использоваться для устранения неоднозначности конфликтов имен, так как некоторые языки клиента (например, Visual Basic), без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="f4902-214">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="f4902-215">Используйте акронимы, если это уместно</span><span class="sxs-lookup"><span data-stu-id="f4902-215">Use acronyms where appropriate</span></span>

<span data-ttu-id="f4902-216">Акронимы, таких как XML не сокращений и широко используются в библиотеках .NET в параметр формы (Xml).</span><span class="sxs-lookup"><span data-stu-id="f4902-216">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="f4902-217">Только хорошо известными, широко известных сокращений.</span><span class="sxs-lookup"><span data-stu-id="f4902-217">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="f4902-218">Используйте PascalCase для имен универсального параметра</span><span class="sxs-lookup"><span data-stu-id="f4902-218">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="f4902-219">Используйте PascalCase для универсального параметра имен в открытых интерфейсах API, в том числе для языка F # — с выходом библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f4902-219">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="f4902-220">В частности, используйте имена, такие как `T`, `U`, `T1`, `T2` для произвольных универсальных параметров и имен имеет смысл, затем F # — с выходом библиотеки используют имена, такие как `Key`, `Value`, `Arg`(но не к примеру, `TKey`).</span><span class="sxs-lookup"><span data-stu-id="f4902-220">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="f4902-221">Используйте PascalCase или camelCase для значений в F # модули и открытые функции</span><span class="sxs-lookup"><span data-stu-id="f4902-221">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="f4902-222">camelCase используется для общих функций, которые предназначены для использования неполное (например, `invalidArg`) и для «функции стандартной коллекции» (например, List.map).</span><span class="sxs-lookup"><span data-stu-id="f4902-222">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="f4902-223">В обоих этих случаях имена функций действуют во многом аналогично ключевых слов языка.</span><span class="sxs-lookup"><span data-stu-id="f4902-223">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="f4902-224">Объект, тип и модуль разработки</span><span class="sxs-lookup"><span data-stu-id="f4902-224">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="f4902-225">Использовать пространства имен или модули для хранения типов и модулей</span><span class="sxs-lookup"><span data-stu-id="f4902-225">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="f4902-226">Каждый файл F # в компоненте должно начинаться с объявления пространства имен либо объявление модуля.</span><span class="sxs-lookup"><span data-stu-id="f4902-226">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="f4902-227">или</span><span class="sxs-lookup"><span data-stu-id="f4902-227">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="f4902-228">Ниже приведены различия между использованием модулей и пространств имен для организации кода на верхнем уровне.</span><span class="sxs-lookup"><span data-stu-id="f4902-228">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="f4902-229">Пространства имен могут охватывать несколько файлов</span><span class="sxs-lookup"><span data-stu-id="f4902-229">Namespaces can span multiple files</span></span>
* <span data-ttu-id="f4902-230">Пространства имен не может содержать функции F #, если они включены в модуль, внутренний</span><span class="sxs-lookup"><span data-stu-id="f4902-230">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="f4902-231">Код для любого заданного модуля должны находиться в пределах одного файла</span><span class="sxs-lookup"><span data-stu-id="f4902-231">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="f4902-232">Модули верхнего уровня может содержать функции F # без необходимости внутренним</span><span class="sxs-lookup"><span data-stu-id="f4902-232">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="f4902-233">Выбор между верхнего уровня пространства имен или модуля влияет на форме скомпилированного кода и таким образом повлияет на представлении из других языков .NET API в конечном итоге следует заполнить вне кода F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-233">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="f4902-234">Использовать методы и свойства для операций встроенные типы объектов</span><span class="sxs-lookup"><span data-stu-id="f4902-234">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="f4902-235">При работе с объектами, рекомендуется убедиться, что использовать функциональные возможности реализуется в виде методам и свойствам этого типа.</span><span class="sxs-lookup"><span data-stu-id="f4902-235">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="f4902-236">Основная часть функции для данного элемента должны обязательно нельзя реализовать этот элемент, но следует использовать часть этой функциональности.</span><span class="sxs-lookup"><span data-stu-id="f4902-236">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="f4902-237">Использование классов, инкапсулирующих изменяемое состояние</span><span class="sxs-lookup"><span data-stu-id="f4902-237">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="f4902-238">В языке F # это действие необходимо выполнить где, состояние не уже инкапсулируется другой языковой конструкции, например, закрытия, выражение последовательности или асинхронное вычисление.</span><span class="sxs-lookup"><span data-stu-id="f4902-238">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="f4902-239">Использовать интерфейсы для группировки связанных операций</span><span class="sxs-lookup"><span data-stu-id="f4902-239">Use interfaces to group related operations</span></span>

<span data-ttu-id="f4902-240">Типы интерфейсов используются для представления ряда операций.</span><span class="sxs-lookup"><span data-stu-id="f4902-240">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="f4902-241">Этот метод является предпочтительным для другие параметры, например кортежей, функций или записей функций.</span><span class="sxs-lookup"><span data-stu-id="f4902-241">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="f4902-242">В ссылке к:</span><span class="sxs-lookup"><span data-stu-id="f4902-242">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

<span data-ttu-id="f4902-243">Интерфейсы являются понятия первого класса .NET, который можно использовать для достижения что Функторы обычно отображаются.</span><span class="sxs-lookup"><span data-stu-id="f4902-243">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="f4902-244">Кроме того они могут использоваться для кодирования типов, существующий в программу, которое не может быть записей функций.</span><span class="sxs-lookup"><span data-stu-id="f4902-244">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="f4902-245">Использовать модуль для групповых функций, которые работают с коллекциями</span><span class="sxs-lookup"><span data-stu-id="f4902-245">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="f4902-246">При определении типа коллекции, подберите стандартный набор операций, например `CollectionType.map` и `CollectionType.iter`) для новых типов коллекций.</span><span class="sxs-lookup"><span data-stu-id="f4902-246">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="f4902-247">Если включить такой модуль, выполните стандартным соглашениям об именовании для функций, содержащихся в FSharp.Core.</span><span class="sxs-lookup"><span data-stu-id="f4902-247">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="f4902-248">Используйте модуль с функциями группу для распространенных канонические функции, особенно в math и библиотеки DSL</span><span class="sxs-lookup"><span data-stu-id="f4902-248">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="f4902-249">Например `Microsoft.FSharp.Core.Operators` является коллекцией автоматически открытых функций верхнего уровня (как `abs` и `sin`), предоставляемые FSharp.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="f4902-249">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="f4902-250">Аналогичным образом, библиотека статистики может включать модуль с функциями `erf` и `erfc`, для которой предназначен этот модуль должен быть открыт автоматически.</span><span class="sxs-lookup"><span data-stu-id="f4902-250">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="f4902-251">Рассмотрите возможность использования RequireQualifiedAccess и тщательно применить атрибуты AutoOpen</span><span class="sxs-lookup"><span data-stu-id="f4902-251">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="f4902-252">Добавление `[<RequireQualifiedAccess>]` атрибут для модуля указывает, что модуль не может быть открыт, и необходимость явной ссылки на элементы модуля полное доступ.</span><span class="sxs-lookup"><span data-stu-id="f4902-252">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="f4902-253">Например `Microsoft.FSharp.Collections.List` модуль имеет этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="f4902-253">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="f4902-254">Это полезно в том случае, когда функции и значения в модуле имеют имена, которые могут вступать в конфликт с именами в других модулях.</span><span class="sxs-lookup"><span data-stu-id="f4902-254">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="f4902-255">Требование полного доступа может значительно повысить удобство поддержки долгосрочной и evolvability библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f4902-255">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="f4902-256">Добавление `[<AutoOpen>]` атрибут к модулю означает модуль будет открываться при открытии содержащего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f4902-256">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="f4902-257">`[<AutoOpen>]` Атрибут также может применяться к сборке, чтобы указать модуль, который автоматически открывается при ссылке на сборку.</span><span class="sxs-lookup"><span data-stu-id="f4902-257">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="f4902-258">Например, Статистика библиотеки **MathsHeaven.Statistics** может содержать `module MathsHeaven.Statistics.Operators` содержащие функции `erf` и `erfc`.</span><span class="sxs-lookup"><span data-stu-id="f4902-258">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="f4902-259">Это целесообразно пометить этот модуль как `[<AutoOpen>]`.</span><span class="sxs-lookup"><span data-stu-id="f4902-259">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="f4902-260">Это означает `open MathsHeaven.Statistics` также откроет этот модуль и перевести имена `erf` и `erfc` в область действия.</span><span class="sxs-lookup"><span data-stu-id="f4902-260">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="f4902-261">Использование другого хорошо `[<AutoOpen>]` для модулей, содержащих методы расширения.</span><span class="sxs-lookup"><span data-stu-id="f4902-261">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="f4902-262">Для связи с чрезмерным использованием `[<AutoOpen>]` приводит к его засорения пространств имен и атрибут должен использоваться с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="f4902-262">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="f4902-263">Для определенных библиотек в отдельные домены, разумно использовать `[<AutoOpen>]` может привести к более удобной.</span><span class="sxs-lookup"><span data-stu-id="f4902-263">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="f4902-264">Рекомендуется определять оператор членов в классах, когда с помощью хорошо известных операторов не соответствует</span><span class="sxs-lookup"><span data-stu-id="f4902-264">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="f4902-265">Иногда классы используются для моделирования математических конструкций, таких как векторов.</span><span class="sxs-lookup"><span data-stu-id="f4902-265">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="f4902-266">Если моделируемый домен содержит хорошо известных операторов, определяя их как члены, встроенная в класс полезен.</span><span class="sxs-lookup"><span data-stu-id="f4902-266">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="f4902-267">В этом руководстве соответствует Общие рекомендации .NET для этих типов.</span><span class="sxs-lookup"><span data-stu-id="f4902-267">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="f4902-268">Тем не менее может быть дополнительно важную роль в F # кодирования, как это позволяет этих типов, которые должны использоваться в методах с ограничениями членов, например List.sumBy и вместе с функциями F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-268">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="f4902-269">Рассмотрите возможность использования CompiledName для предоставления. NET-понятное имя для других потребителей языков .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-269">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="f4902-270">Иногда может потребоваться назвать в один стиль для потребителей F # (такие как статический член в нижнем регистре, чтобы он располагался как если бы функция привязкой модуля), но имеют другой стиль для имени, если он компилируется в сборку.</span><span class="sxs-lookup"><span data-stu-id="f4902-270">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="f4902-271">Можно использовать `[<CompiledName>]` атрибут для предоставления другой стиль для кода не F #, использование сборки.</span><span class="sxs-lookup"><span data-stu-id="f4902-271">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="f4902-272">С помощью `[<CompiledName>]`, соглашения об именовании .NET можно использовать для пользователей без F # сборки.</span><span class="sxs-lookup"><span data-stu-id="f4902-272">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="f4902-273">Используйте перегрузки метода для функций-членов, если это позволяет достичь более простой API</span><span class="sxs-lookup"><span data-stu-id="f4902-273">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="f4902-274">Перегрузка метода является мощным средством для упрощения API, который может потребоваться выполнить аналогичные функциональные возможности, но различные параметры и аргументы.</span><span class="sxs-lookup"><span data-stu-id="f4902-274">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="f4902-275">В языке F # чаще для перегрузки на количество аргументов, а не типы аргументов.</span><span class="sxs-lookup"><span data-stu-id="f4902-275">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="f4902-276">Скрыть представления типы объединений и записи, если вероятно эволюционирование разработки этих типов</span><span class="sxs-lookup"><span data-stu-id="f4902-276">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="f4902-277">Избегайте раскрытия конкретного представления объектов.</span><span class="sxs-lookup"><span data-stu-id="f4902-277">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="f4902-278">Например, конкретная представление <xref:System.DateTime> значения не показывается внешних, открытый API для разработки библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-278">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="f4902-279">Во время выполнения общеязыковая среда выполнения знает зафиксированных реализацию, которая будет использоваться на протяжении выполнения.</span><span class="sxs-lookup"><span data-stu-id="f4902-279">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="f4902-280">Тем не менее скомпилированный код не сам получают зависимостей от конкретного представления.</span><span class="sxs-lookup"><span data-stu-id="f4902-280">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="f4902-281">Избегайте использования наследование реализации для расширяемости</span><span class="sxs-lookup"><span data-stu-id="f4902-281">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="f4902-282">В языке F # наследование реализации используется редко.</span><span class="sxs-lookup"><span data-stu-id="f4902-282">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="f4902-283">Кроме того часто иерархий наследования являются сложными и сложным для изменения при поступлении новых требований.</span><span class="sxs-lookup"><span data-stu-id="f4902-283">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="f4902-284">Реализация наследования по-прежнему существует в языке F # для совместимости и в редких случаях это лучшее решение проблемы, однако альтернативные методы, необходимо обратиться в программах F #, при разработке для полиморфизма, например реализацию интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f4902-284">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="f4902-285">Функции и член подписи</span><span class="sxs-lookup"><span data-stu-id="f4902-285">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="f4902-286">Используйте кортежей для возвращаемых значений, если возвращается небольшое количество несколько несвязанных значений</span><span class="sxs-lookup"><span data-stu-id="f4902-286">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="f4902-287">Вот хороший пример использования кортеж в тип возвращаемого значения:</span><span class="sxs-lookup"><span data-stu-id="f4902-287">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="f4902-288">Для возврата типов, содержащих множество компонентов или где компоненты относятся к одной сущности характера, рассмотрите возможность использования именованного типа вместо кортеж.</span><span class="sxs-lookup"><span data-stu-id="f4902-288">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="f4902-289">Используйте `Async<T>` для асинхронного программирования на границах API F #</span><span class="sxs-lookup"><span data-stu-id="f4902-289">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="f4902-290">Если имеется соответствующий синхронную операцию с именем `Operation` , возвращающий `T`, то должен быть назван асинхронной операции `AsyncOperation` если он возвращает `Async<T>` или `OperationAsync` если он возвращает `Task<T>`.</span><span class="sxs-lookup"><span data-stu-id="f4902-290">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="f4902-291">Для часто используемых типов .NET, предоставляющих методов Begin и End, рассмотрите возможность использования `Async.FromBeginEnd` для записи методы расширения в качестве оболочки для предоставления F # асинхронную модель программирования этих интерфейсов API .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-291">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

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

### <a name="exceptions"></a><span data-ttu-id="f4902-292">Исключения</span><span class="sxs-lookup"><span data-stu-id="f4902-292">Exceptions</span></span>

<span data-ttu-id="f4902-293">Исключениями являются исключительные в .NET; то есть они не должно происходить часто во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f4902-293">Exceptions are exceptional in .NET; that is, they should not occur frequently at runtime.</span></span> <span data-ttu-id="f4902-294">После этого полезные сведения, содержащиеся в них.</span><span class="sxs-lookup"><span data-stu-id="f4902-294">When they do, the information they contain is valuable.</span></span> <span data-ttu-id="f4902-295">Исключения — это основное понятие первого класса .NET; поэтому ИТ следующим образом, соответствующие приложения исключений следует использовать как часть конструктора интерфейса компонента.</span><span class="sxs-lookup"><span data-stu-id="f4902-295">Exceptions are a core first class concept of .NET; it hence follows that appropriate application of the Exceptions should be used as part of the design of the interface of a component.</span></span>

#### <a name="follow-the-net-guidelines-for-exceptions"></a><span data-ttu-id="f4902-296">Следуйте инструкциям для исключений .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-296">Follow the .NET guidelines for exceptions</span></span>

<span data-ttu-id="f4902-297">[Правилам разработки библиотеки .NET](../../standard/design-guidelines/exceptions.md) предоставить отличные советы по использованию исключения в контексте всех программирования .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-297">The [.NET Library Design Guidelines](../../standard/design-guidelines/exceptions.md) give excellent advice on the use of exceptions in the context of all .NET programming.</span></span> <span data-ttu-id="f4902-298">Из этих инструкций входят следующие:</span><span class="sxs-lookup"><span data-stu-id="f4902-298">Some of these guidelines are as follows:</span></span>

* <span data-ttu-id="f4902-299">Не используйте исключения для обычного потока управления.</span><span class="sxs-lookup"><span data-stu-id="f4902-299">Do not use exceptions for normal flow of control.</span></span> <span data-ttu-id="f4902-300">Несмотря на то, что этот метод часто используется в таких языках, как OCaml, он часто встречаются ошибки и может быть неэффективным на платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-300">Although this technique is often used in languages such as OCaml, it is bug-prone and can be inefficient on .NET.</span></span> <span data-ttu-id="f4902-301">Вместо этого рассмотрите возможность возврата `None` параметра значение, указывающее на сбой, — это общие или ожидаемых дело.</span><span class="sxs-lookup"><span data-stu-id="f4902-301">Instead, consider returning a `None` option value to indicate a failure that is a common or expected occurrence.</span></span>

* <span data-ttu-id="f4902-302">Документ исключений для компонентов, если функция используется неправильно.</span><span class="sxs-lookup"><span data-stu-id="f4902-302">Document exceptions thrown by your components when a function is used incorrectly.</span></span>

* <span data-ttu-id="f4902-303">Если это возможно, использовать существующие исключения из пространства имен System.</span><span class="sxs-lookup"><span data-stu-id="f4902-303">Where possible, employ existing exceptions from the System namespaces.</span></span> <span data-ttu-id="f4902-304">Избегайте <xref:System.ApplicationException>, хотя.</span><span class="sxs-lookup"><span data-stu-id="f4902-304">Avoid <xref:System.ApplicationException>, though.</span></span>

* <span data-ttu-id="f4902-305">Не вызывайте <xref:System.Exception> при escape для пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="f4902-305">Do not throw <xref:System.Exception> when it will escape to user code.</span></span> <span data-ttu-id="f4902-306">Сюда входят избегать использования `failwith`, `failwithf`, которая — это удобные функции для использования при создании сценариев и для разрабатываемого кода, но должны быть удалены из кода библиотеки F # пользу генерации более конкретный тип исключения.</span><span class="sxs-lookup"><span data-stu-id="f4902-306">This includes avoiding the use of `failwith`, `failwithf`, which are handy functions for use in scripting and for code under development, but should be removed from F# library code in favor of throwing a more specific exception type.</span></span>

* <span data-ttu-id="f4902-307">Используйте `nullArg`, `invalidArg`, и `invalidOp` в качестве механизма для вызова <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, и <xref:System.InvalidOperationException> при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f4902-307">Use `nullArg`, `invalidArg`, and `invalidOp` as the mechanism to throw <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, and <xref:System.InvalidOperationException> when appropriate.</span></span>

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a><span data-ttu-id="f4902-308">Рассмотрите возможность использования значения параметров для возвращаемых типов, когда сбой не является исключительной ситуации.</span><span class="sxs-lookup"><span data-stu-id="f4902-308">Consider using option values for return types when failure is not an exceptional scenario</span></span>

<span data-ttu-id="f4902-309">Является подход с использованием .NET для исключения, они должны быть «исключительные»; то есть их следует выполнять относительно редко.</span><span class="sxs-lookup"><span data-stu-id="f4902-309">The .NET approach to exceptions is that they should be “exceptional”; that is, they should occur relatively infrequently.</span></span> <span data-ttu-id="f4902-310">Однако некоторые операции (например, поиск таблицы) может не часто.</span><span class="sxs-lookup"><span data-stu-id="f4902-310">However, some operations (for example, searching a table) may fail frequently.</span></span> <span data-ttu-id="f4902-311">Значения параметров в F # являются отличным способом представляют типы возвращаемого значения этих операций.</span><span class="sxs-lookup"><span data-stu-id="f4902-311">F# option values are an excellent way to represent the return types of these operations.</span></span> <span data-ttu-id="f4902-312">Эти операции обычно начинаются с префикса имени «try»:</span><span class="sxs-lookup"><span data-stu-id="f4902-312">These operations conventionally start with the name prefix “try”:</span></span>

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a><span data-ttu-id="f4902-313">Члены расширений</span><span class="sxs-lookup"><span data-stu-id="f4902-313">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="f4902-314">Тщательно применить члены расширений F # в F #-к-компоненты F #</span><span class="sxs-lookup"><span data-stu-id="f4902-314">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="f4902-315">Члены расширений F #, обычно только используется в для операций, находящиеся в замыкании внутренних операций, связанных с типом, в большинстве режимов его использования.</span><span class="sxs-lookup"><span data-stu-id="f4902-315">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="f4902-316">Как правило — обеспечить API, которые являются более устойчивым к F # для различных типов .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-316">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="f4902-317">Типы объединения</span><span class="sxs-lookup"><span data-stu-id="f4902-317">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="f4902-318">Вместо иерархии классов древовидной структурой данных следует использовать размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="f4902-318">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="f4902-319">Древовидной структуры являются рекурсивно определяемые.</span><span class="sxs-lookup"><span data-stu-id="f4902-319">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="f4902-320">Это неудобно с наследованием, но элегантное с размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="f4902-320">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="f4902-321">Представления данных древовидной с размеченные объединения также позволяет использовать преимущества exhaustiveness в сопоставлениях с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="f4902-321">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="f4902-322">Используйте `[<RequireQualifiedAccess>]` на регистра, имена которых не являются достаточно уникальными типы объединения</span><span class="sxs-lookup"><span data-stu-id="f4902-322">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="f4902-323">Тратится время в домене, где то же имя — это наиболее имя для выполнения различных задач, таких как случаи размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="f4902-323">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="f4902-324">Можно использовать `[<RequireQualifiedAccess>]` для однозначного определения вариантов имена во избежание запуска путаницу ошибок из-за затенения зависит от порядка `open` инструкций</span><span class="sxs-lookup"><span data-stu-id="f4902-324">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="f4902-325">Скрыть представления размеченные объединения для двоичного совместимые интерфейсы API, если вероятно эволюционирование разработки этих типов</span><span class="sxs-lookup"><span data-stu-id="f4902-325">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="f4902-326">Типы объединений полагаться на F # подборе шаблонов форм для краткости модели программирования.</span><span class="sxs-lookup"><span data-stu-id="f4902-326">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="f4902-327">Как упоминалось ранее, следует избегать раскрытия представления конкретных данных, если может развиваться разработки этих типов.</span><span class="sxs-lookup"><span data-stu-id="f4902-327">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="f4902-328">Например, представление размеченного объединения могут быть скрыты с помощью объявление закрытого или внутреннего или с помощью файла подписи.</span><span class="sxs-lookup"><span data-stu-id="f4902-328">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="f4902-329">При выводе размеченные объединения беспорядочно, может оказаться неудобным для версии библиотеки без нарушения кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="f4902-329">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="f4902-330">Вместо этого рассмотрите возможность предоставления одного или нескольких активных шаблонов, позволяющая сопоставления над значениями типа шаблона.</span><span class="sxs-lookup"><span data-stu-id="f4902-330">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="f4902-331">Активные шаблоны предоставляют альтернативный способ предоставления потребители F # с помощью шаблона при этом избежать предоставления непосредственно типы объединения F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-331">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="f4902-332">Встроенные функции и ограничения элементов</span><span class="sxs-lookup"><span data-stu-id="f4902-332">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="f4902-333">Определение универсального числовые алгоритмы, с помощью встроенных функций с ограничениями подразумеваемых членов и статически разрешаемые универсальных типов</span><span class="sxs-lookup"><span data-stu-id="f4902-333">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="f4902-334">Арифметические член ограничения и ограничения сравнения F # — это стандарт для программирование на F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-334">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="f4902-335">Рассмотрим следующий пример кода:</span><span class="sxs-lookup"><span data-stu-id="f4902-335">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="f4902-336">Тип функции выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f4902-336">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="f4902-337">Это подходящая функция для открытого API в математическую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="f4902-337">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="f4902-338">Старайтесь не использовать ограничения элементов для моделирования классов типа и типизация</span><span class="sxs-lookup"><span data-stu-id="f4902-338">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="f4902-339">Можно имитировать «типизация» с помощью ограничения элементов F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-339">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="f4902-340">Однако члены, которые делают с помощью данного объекта не поддерживается в общие используется в F #-к-проекты библиотеки F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-340">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="f4902-341">Это происходит потому библиотеки макетов на основе неявных ограничений незнакомых или стандартным приводят к появлению код пользователя, становятся неудобными и привязан к шаблону одной конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="f4902-341">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="f4902-342">Кроме того является вполне вероятно, что активно использовать ограничения элементов таким образом может привести к компиляции очень много времени.</span><span class="sxs-lookup"><span data-stu-id="f4902-342">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="f4902-343">Определения операторов</span><span class="sxs-lookup"><span data-stu-id="f4902-343">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="f4902-344">Не рекомендуется определять пользовательские операторы, символьные</span><span class="sxs-lookup"><span data-stu-id="f4902-344">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="f4902-345">Пользовательские операторы необходимы в некоторых ситуациях и очень полезных обозначениям устройства в пределах большая часть кода реализации.</span><span class="sxs-lookup"><span data-stu-id="f4902-345">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="f4902-346">Для новых пользователей библиотеки именованных функций зачастую проще использовать.</span><span class="sxs-lookup"><span data-stu-id="f4902-346">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="f4902-347">Кроме того пользовательские символьных операторы могут быть трудными для документа, и пользователи находят более сложным для поиска справки по операторам, из-за существующих ограничений обработчиков интегрированной среды разработки и поиска.</span><span class="sxs-lookup"><span data-stu-id="f4902-347">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="f4902-348">Поэтому рекомендуется для публикации в виде именованных функций и членов и дополнительно предоставляют операторы для этой функции только в том случае, если значимых преимуществ перевешивают документации и когнитивных затраты на их наличие.</span><span class="sxs-lookup"><span data-stu-id="f4902-348">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="f4902-349">Единицы измерения</span><span class="sxs-lookup"><span data-stu-id="f4902-349">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="f4902-350">Тщательно единицы измерения используются в целях безопасности добавлен тип в коде F #</span><span class="sxs-lookup"><span data-stu-id="f4902-350">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="f4902-351">Дополнительные сведения о типизации для единицы измерения удаляется при просмотре в других языках .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-351">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="f4902-352">Помните, что компоненты .NET, инструменты и отражения будет видна типы сетей SAN единицы.</span><span class="sxs-lookup"><span data-stu-id="f4902-352">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="f4902-353">Например, C# пользователи увидят `float` вместо `float<kg>`.</span><span class="sxs-lookup"><span data-stu-id="f4902-353">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="f4902-354">Сокращенные обозначения типов</span><span class="sxs-lookup"><span data-stu-id="f4902-354">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="f4902-355">Внимательно используйте сокращенные обозначения типов для упрощения кода F #</span><span class="sxs-lookup"><span data-stu-id="f4902-355">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="f4902-356">Сокращенные имена типов не будут видеть отражения, средства и компоненты .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-356">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="f4902-357">Значительный объем сокращенные обозначения типов также можно сделать домена отображаются сложнее, чем фактически является, которой может запутать потребителей.</span><span class="sxs-lookup"><span data-stu-id="f4902-357">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="f4902-358">Избегайте сокращенные обозначения типов для открытых типов, членов и свойства должны различаться по своей природе с доступными в сокращаемом</span><span class="sxs-lookup"><span data-stu-id="f4902-358">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="f4902-359">В этом случае сокращаемом раскроется много о представление, определенное фактический тип.</span><span class="sxs-lookup"><span data-stu-id="f4902-359">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="f4902-360">Вместо этого рассмотрите возможность упаковки сокращение в тип класса или одиночным размеченного объединения (или когда важна производительность, рассмотрите возможность использования типа struct сокращенное название программы-оболочки).</span><span class="sxs-lookup"><span data-stu-id="f4902-360">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="f4902-361">Например — заманчивой определить несколькими карты как особый случай F # карты, например:</span><span class="sxs-lookup"><span data-stu-id="f4902-361">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="f4902-362">Тем не менее операции логического обозначении для данного типа не совпадают, как операции на карте — например, это целесообразно, чтобы оператор lookup сопоставлены. [ключа] возвращают пустой список, если ключа нет в словаре, а не вызывая исключение.</span><span class="sxs-lookup"><span data-stu-id="f4902-362">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="f4902-363">Рекомендации для библиотек для использования из других языков .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-363">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="f4902-364">При разработке библиотеки для использования из других языков .NET, очень важно следовать [правилам разработки библиотеки .NET](../../standard/design-guidelines/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4902-364">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="f4902-365">В этом документе, эти библиотеки помечены как соответствующего ванили библиотеки .NET, в отличие от F # — с выходом библиотек, которые используются в языке F # создает без ограничений.</span><span class="sxs-lookup"><span data-stu-id="f4902-365">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="f4902-366">Проектирование соответствующего ванили библиотек .NET означает предоставление знакомых и идиоматическое API, согласованное с оставшейся частью .NET Framework, сводя к минимуму использование F #-конкретных конструкций в открытом API.</span><span class="sxs-lookup"><span data-stu-id="f4902-366">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="f4902-367">В следующих разделах описываются правила.</span><span class="sxs-lookup"><span data-stu-id="f4902-367">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="f4902-368">Пространство имен и тип конструктора (для библиотек для использования из других языков .NET)</span><span class="sxs-lookup"><span data-stu-id="f4902-368">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="f4902-369">Соблюдать правила именования .NET для открытого API-интерфейса компонентов</span><span class="sxs-lookup"><span data-stu-id="f4902-369">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="f4902-370">Обратите внимание на использование сокращенного названия и правила использования прописных букв .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-370">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="f4902-371">Использовать пространства имен, типов и членов в качестве основной организационной структурой для компонентов</span><span class="sxs-lookup"><span data-stu-id="f4902-371">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="f4902-372">Все файлы, содержащие открытые функциональные возможности должна начинаться с `namespace` объявления только общедоступные сущности в пространствах имен следует и типы.</span><span class="sxs-lookup"><span data-stu-id="f4902-372">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="f4902-373">Не используйте модули F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-373">Do not use F# modules.</span></span>

<span data-ttu-id="f4902-374">Используйте неоткрытые модули для размещения код реализации, служебные типы и служебных функций.</span><span class="sxs-lookup"><span data-stu-id="f4902-374">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="f4902-375">Статические типы имеют преимущество перед модули, поскольку они позволяют будущих развитие API-интерфейса для использования перегрузки и другие концепции проектирования .NET API, которые не могут быть использованы в модулях F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-375">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="f4902-376">Например, вместо открытый API:</span><span class="sxs-lookup"><span data-stu-id="f4902-376">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="f4902-377">Рекомендуется вместо:</span><span class="sxs-lookup"><span data-stu-id="f4902-377">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="f4902-378">Используйте типы записи F # в ванильные API-интерфейсы .NET, если не будет развиваться конструктора типов</span><span class="sxs-lookup"><span data-stu-id="f4902-378">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="f4902-379">Типы записей F #, компилируются в простой класс .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-379">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="f4902-380">Это подходит для некоторых типов простой и стабильность в API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="f4902-380">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="f4902-381">Следует рассмотреть возможность использования `[<NoEquality>]` и `[<NoComparison>]` атрибуты, чтобы отключить автоматическое создание интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f4902-381">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="f4902-382">Также Избегайте поля изменяемых записей в ванильные API-интерфейсы .NET как эти предоставляет доступ к открытым полем.</span><span class="sxs-lookup"><span data-stu-id="f4902-382">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="f4902-383">Всегда учитывайте, будет ли класс предоставляют более гибкий вариант будущих развитие API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f4902-383">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="f4902-384">Например следующий код F # предоставляет открытый API для потребителя, C#:</span><span class="sxs-lookup"><span data-stu-id="f4902-384">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="f4902-385">F #:</span><span class="sxs-lookup"><span data-stu-id="f4902-385">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

<span data-ttu-id="f4902-386">C#:</span><span class="sxs-lookup"><span data-stu-id="f4902-386">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="f4902-387">Скрыть представление типов F # объединения в ванильные API-интерфейсы .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-387">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="f4902-388">Типы объединения F # обычно не используется за границы компонентов даже для F #-к-F # кодирования.</span><span class="sxs-lookup"><span data-stu-id="f4902-388">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="f4902-389">Это устройство отлично реализации при использовании внутри в компоненты и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f4902-389">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="f4902-390">При разработке ванильные .NET API, можно спрятать представление типа объединения с помощью объявления private или файл сигнатур.</span><span class="sxs-lookup"><span data-stu-id="f4902-390">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="f4902-391">Вы также может быть расширено типов, которые внутренне используют объединения представление с элементами для обеспечения требуемой. С выходом NET API.</span><span class="sxs-lookup"><span data-stu-id="f4902-391">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="f4902-392">Проектирование графического пользовательского интерфейса и другими компонентами с помощью шаблонов проектирования платформы</span><span class="sxs-lookup"><span data-stu-id="f4902-392">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="f4902-393">Существует множество различных платформ в .NET, таких как ASP.NET, WPF и WinForms.</span><span class="sxs-lookup"><span data-stu-id="f4902-393">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="f4902-394">Соглашения об именовании и проектирования для каждого следует использовать при разработке компонентов, используемых в этих платформ.</span><span class="sxs-lookup"><span data-stu-id="f4902-394">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="f4902-395">Например для программирования WPF, применяйте предусмотренные WPF принципы разработки классов, которые вы разрабатываете.</span><span class="sxs-lookup"><span data-stu-id="f4902-395">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="f4902-396">Для моделей в программирование пользовательского интерфейса используйте шаблоны проектирования, таких как события и коллекций, основанных на уведомления, например в <xref:System.Collections.ObjectModel>.</span><span class="sxs-lookup"><span data-stu-id="f4902-396">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="f4902-397">Объекты и элементы проектирования (для библиотек для использования из других языков .NET)</span><span class="sxs-lookup"><span data-stu-id="f4902-397">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="f4902-398">Используется для предоставления событий .NET CLIEvent-атрибут</span><span class="sxs-lookup"><span data-stu-id="f4902-398">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="f4902-399">Создать `DelegateEvent` с определенной версии .NET типа, которая принимает объект делегата и `EventArgs` (вместо `Event`, с использованием `FSharpHandler` типа по умолчанию), чтобы события, опубликованные в знакомой для других языков .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-399">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="f4902-400">Предоставлять асинхронные операции как методы, которые возвращают задач .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-400">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="f4902-401">Задачи используются в .NET для представления активных асинхронных вычислений.</span><span class="sxs-lookup"><span data-stu-id="f4902-401">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="f4902-402">Задачи — в целом менее композиционная, чем F # `Async<T>` объектов, так как они представляют задачи «уже выполняется» и не может состоять вместе способами, параллельные построения или которой скрыть распространение сигналы отмены и другие контекстные параметры.</span><span class="sxs-lookup"><span data-stu-id="f4902-402">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="f4902-403">Тем не менее несмотря на это, методы, которые возвращают задачи — это стандартное представление об асинхронном программировании на платформе .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-403">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="f4902-404">Вы будете часто Обраб явного токена отмены:</span><span class="sxs-lookup"><span data-stu-id="f4902-404">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="f4902-405">Использовать типы делегатов .NET вместо функции типов F #</span><span class="sxs-lookup"><span data-stu-id="f4902-405">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="f4902-406">Здесь «типы функции F #» означает «стрелка» типов, таких как `int -> int`.</span><span class="sxs-lookup"><span data-stu-id="f4902-406">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="f4902-407">Вместо этого:</span><span class="sxs-lookup"><span data-stu-id="f4902-407">Instead of this:</span></span>

```fsharp
member this.Transform(f:int->int) =
    ...
```

<span data-ttu-id="f4902-408">Выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="f4902-408">Do this:</span></span>

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

<span data-ttu-id="f4902-409">Тип функции F # отображается в виде `class FSharpFunc<T,U>` с другими языками .NET и менее подходящим для языковые возможности и средства, которые понимать типы делегата.</span><span class="sxs-lookup"><span data-stu-id="f4902-409">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="f4902-410">При создании метода более высокого порядка, предназначенных для .NET Framework 3.5 или более поздней версии, `System.Func` и `System.Action` делегаты являются вправо API-интерфейсы для публикации позволяет разработчикам .NET использовать эти API-интерфейсы в виде трения низкий.</span><span class="sxs-lookup"><span data-stu-id="f4902-410">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="f4902-411">(При разработке для .NET Framework 2.0, типы делегатов системные более ограничены; следует использовать предопределенный делегат типы, такие как `System.Converter<T,U>` или определение определенному типу делегата.)</span><span class="sxs-lookup"><span data-stu-id="f4902-411">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="f4902-412">С другой стороны, делегаты .NET не являются естественным для языка F #-с выходом библиотеки (см. следующий раздел на F #-с выходом библиотек).</span><span class="sxs-lookup"><span data-stu-id="f4902-412">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="f4902-413">В результате общие стратегии реализации при разработке более высокого порядка методы для соответствующего ванили библиотек .NET является создание всех реализации, с помощью функции типы F #, а затем создать открытый интерфейс API, с помощью делегатов как тонкой оболочкой поверх фактическое F # Реализация.</span><span class="sxs-lookup"><span data-stu-id="f4902-413">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="f4902-414">Использовать шаблон TryGetValue вместо возвращения значения параметров F # и выбрать предпочтительные перегрузки метода принимать значения параметров F # в качестве аргументов</span><span class="sxs-lookup"><span data-stu-id="f4902-414">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="f4902-415">Общие шаблоны использования для типа параметра F # в API-интерфейсы предпочтительнее реализации в ванильные методы разработки с помощью стандартных .NET API-интерфейсы .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-415">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="f4902-416">Вместо возвращения значения параметра F #, рассмотрите возможность использования возвращаемый тип bool, а также как шаблон «TryGetValue» выходной параметр.</span><span class="sxs-lookup"><span data-stu-id="f4902-416">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="f4902-417">И, а F # значения параметра в качестве параметров, рассмотрите возможность использования перегрузки метода или необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="f4902-417">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="f4902-418">Используйте интерфейс коллекции .NET типы IEnumerable\<T\> и IDictionary\<ключ, значение\> для параметров и возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="f4902-418">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="f4902-419">Избегайте использования конкретных типах коллекций например массивов .NET `T[]`, типы F # `list<T>`, `Map<Key,Value>` и `Set<T>`, и .NET конкретные типы коллекций, такие как `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="f4902-419">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="f4902-420">Согласно правилам разработки библиотеки .NET имеют хороший совет о необходимости использования различных типов коллекций, такие как `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="f4902-420">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="f4902-421">Некоторые использование массивов (`T[]`) допустима в некоторых случаях на территории производительности.</span><span class="sxs-lookup"><span data-stu-id="f4902-421">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="f4902-422">Обратите внимание, особенно, `seq<T>` является просто F # псевдоним для `IEnumerable<T>`, и, следовательно seq часто соответствующего типа нужна .NET API.</span><span class="sxs-lookup"><span data-stu-id="f4902-422">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="f4902-423">Вместо F # списки:</span><span class="sxs-lookup"><span data-stu-id="f4902-423">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names : string list) =
    ...
```

<span data-ttu-id="f4902-424">Использование последовательностей F #:</span><span class="sxs-lookup"><span data-stu-id="f4902-424">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="f4902-425">Используйте тип единицы измерения как единственный входной тип метода в определении нулевой аргумент метода или как единственный возвращаемый тип для определения метода, возвращающего void</span><span class="sxs-lookup"><span data-stu-id="f4902-425">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="f4902-426">Избегайте другим пользователям типа единицы.</span><span class="sxs-lookup"><span data-stu-id="f4902-426">Avoid other uses of the unit type.</span></span> <span data-ttu-id="f4902-427">Это хорошо.</span><span class="sxs-lookup"><span data-stu-id="f4902-427">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

<span data-ttu-id="f4902-428">Это неправильный:</span><span class="sxs-lookup"><span data-stu-id="f4902-428">This is bad:</span></span>

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="f4902-429">Проверку наличия значений null в пределах границ соответствующего ванили .NET API</span><span class="sxs-lookup"><span data-stu-id="f4902-429">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="f4902-430">Реализация кода F #, как правило, имеют меньшее количество значений null, из-за шаблоны неизменяемый проектирования и ограничения на использование литералов null для типов F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-430">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="f4902-431">Других языков .NET часто используют значение null гораздо более часто.</span><span class="sxs-lookup"><span data-stu-id="f4902-431">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="f4902-432">По этой причине кода F #, точкой ванильные .NET API необходимо проверить параметры со значением NULL на границе API и запретить поступающих глубже в код F #, реализация этих значений.</span><span class="sxs-lookup"><span data-stu-id="f4902-432">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="f4902-433">`isNull` Функции или сопоставления шаблонов `null` шаблон может использоваться.</span><span class="sxs-lookup"><span data-stu-id="f4902-433">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="f4902-434">Избегайте использования кортежи в качестве возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="f4902-434">Avoid using tuples as return values</span></span>

<span data-ttu-id="f4902-435">Вместо этого предпочтительно, возвращая именованный тип хранения статистических данных или использование выходных параметров, чтобы возвращать несколько значений.</span><span class="sxs-lookup"><span data-stu-id="f4902-435">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="f4902-436">Хотя кортежи и кортежи, структуры в .NET (в том числе поддержка языков C# для кортежей структуры), они чаще всего не даст идеальный и ожидаемый интерфейс API для разработчиков .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-436">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="f4902-437">Избегайте использования каррирования параметров</span><span class="sxs-lookup"><span data-stu-id="f4902-437">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="f4902-438">Используйте соглашения о вызовах .NET ``Method(arg1,arg2,…,argN)``.</span><span class="sxs-lookup"><span data-stu-id="f4902-438">Instead, use .NET calling conventions ``Method(arg1,arg2,…,argN)``.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="f4902-439">Совет: Если вы разрабатываете библиотеки для использования в любом языке .NET, то нет возможно только при этом некоторые экспериментальный C# и Visual Basic программирования для убедитесь, что библиотеки «вид справа» из этих языков.</span><span class="sxs-lookup"><span data-stu-id="f4902-439">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="f4902-440">Также можно использовать средства, такие как .NET Reflector и обозреватель объектов Visual Studio для того, библиотеки и соответствующей документации отображалось должным образом для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="f4902-440">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="f4902-441">Приложение</span><span class="sxs-lookup"><span data-stu-id="f4902-441">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="f4902-442">Законченный пример создания кода F # для использования с другими языками .NET</span><span class="sxs-lookup"><span data-stu-id="f4902-442">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="f4902-443">Рассмотрим следующий класс:</span><span class="sxs-lookup"><span data-stu-id="f4902-443">Consider the following class:</span></span>

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

<span data-ttu-id="f4902-444">Выведенный тип F # этого класса выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f4902-444">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="f4902-445">Давайте рассмотрим, как этот тип F # вид программисту, используя другой язык .NET.</span><span class="sxs-lookup"><span data-stu-id="f4902-445">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="f4902-446">Например приблизительное C# «подпись» выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f4902-446">For example, the approximate C# “signature” is as follows:</span></span>

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

<span data-ttu-id="f4902-447">Существуют некоторые важные особенности как F # представляет конструкции здесь.</span><span class="sxs-lookup"><span data-stu-id="f4902-447">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="f4902-448">Пример:</span><span class="sxs-lookup"><span data-stu-id="f4902-448">For example:</span></span>

* <span data-ttu-id="f4902-449">Метаданные, такие как имена аргументов был сохранен.</span><span class="sxs-lookup"><span data-stu-id="f4902-449">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="f4902-450">Методы F #, которые принимают два аргумента становятся методы C#, которые принимают два аргумента.</span><span class="sxs-lookup"><span data-stu-id="f4902-450">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="f4902-451">Функции и списки становятся ссылки на соответствующие типы в библиотеке F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-451">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="f4902-452">Ниже показано, как настроить этот код необходимо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="f4902-452">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="f4902-453">Выведенный тип F # код выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f4902-453">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="f4902-454">Подпись C# — теперь следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f4902-454">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="f4902-455">Чтобы подготовить к использованию этого типа, как часть соответствующего ванили библиотеки .NET, как показано ниже внесены исправления:</span><span class="sxs-lookup"><span data-stu-id="f4902-455">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="f4902-456">Изменены имена нескольких: `Point1`, `n`, `l`, и `f` стала `RadialPoint`, `count`, `factor`, и `transform`соответственно.</span><span class="sxs-lookup"><span data-stu-id="f4902-456">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="f4902-457">Используемый тип возвращаемого значения `seq<RadialPoint>` вместо `RadialPoint list` , изменив создания списка с помощью `[ ... ]` построения последовательности с помощью `IEnumerable<RadialPoint>`.</span><span class="sxs-lookup"><span data-stu-id="f4902-457">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="f4902-458">Используемый тип делегата .NET `System.Func` вместо типа функции F #.</span><span class="sxs-lookup"><span data-stu-id="f4902-458">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="f4902-459">Это позволяет гораздо лучше использовать в коде C#.</span><span class="sxs-lookup"><span data-stu-id="f4902-459">This makes it far nicer to consume in C# code.</span></span>
