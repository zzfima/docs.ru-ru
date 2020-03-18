---
title: Глобализация и локализация приложений .NET
ms.date: 06/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
ms.openlocfilehash: eae1c38c2383d13bfb4dab83f2fe9551970b39f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120888"
---
# <a name="globalizing-and-localizing-net-applications"></a><span data-ttu-id="c6507-102">Глобализация и локализация приложений .NET</span><span class="sxs-lookup"><span data-stu-id="c6507-102">Globalizing and localizing .NET applications</span></span>

<span data-ttu-id="c6507-103">Разработка международного приложения, в том числе приложения, которое можно локализовать на один или несколько языков, включает следующие шаги: глобализацию, анализ локализуемости и локализацию.</span><span class="sxs-lookup"><span data-stu-id="c6507-103">Developing a world-ready application, including an application that can be localized into one or more languages, involves three steps: globalization, localizability review, and localization.</span></span>

[<span data-ttu-id="c6507-104">Глобализация</span><span class="sxs-lookup"><span data-stu-id="c6507-104">Globalization</span></span>](globalization.md)

<span data-ttu-id="c6507-105">Этот шаг включает проектирование и программирование приложения, не зависящего от языка и региональных параметров и поддерживающего локализованные пользовательские интерфейсы и региональные данные для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="c6507-105">This step involves designing and coding an application that is culture-neutral and language-neutral, and that supports localized user interfaces and regional data for all users.</span></span> <span data-ttu-id="c6507-106">Это предполагает принятие проектных и программных решений, которые не основаны на предположениях в отношении определенного языка или региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c6507-106">It involves making design and programming decisions that are not based on culture-specific assumptions.</span></span> <span data-ttu-id="c6507-107">Хотя глобализованное приложение не локализовано, однако оно разработано и составлено так, чтобы впоследствии его можно было относительно легко локализовать на один или несколько языков.</span><span class="sxs-lookup"><span data-stu-id="c6507-107">While a globalized application is not localized, it nevertheless is designed and written so that it can be subsequently localized into one or more languages with relative ease.</span></span>

[<span data-ttu-id="c6507-108">Проверка локализуемости</span><span class="sxs-lookup"><span data-stu-id="c6507-108">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="c6507-109">Этот шаг позволяет проверить код и дизайн приложения, чтобы убедиться в возможности простой локализации приложения и убедиться, что исполняемый код и ресурсы приложения разделены.</span><span class="sxs-lookup"><span data-stu-id="c6507-109">This step involves reviewing an application's code and design to ensure that it can be localized easily and to identify potential roadblocks for localization, and verifying that the application's executable code is separated from its resources.</span></span> <span data-ttu-id="c6507-110">Если этап глобализации был эффективным, анализ локализуемости подтвердит проектные решения и решения кодирования, принятые во время глобализации.</span><span class="sxs-lookup"><span data-stu-id="c6507-110">If the globalization stage was effective, the localizability review will confirm the design and coding choices made during globalization.</span></span> <span data-ttu-id="c6507-111">На этапе анализа локализуемости можно выявить оставшиеся проблемы, чтобы не пришлось менять исходный код приложения на этапе локализации.</span><span class="sxs-lookup"><span data-stu-id="c6507-111">The localizability stage may also identify any remaining issues so that an application's source code doesn't have to be modified during the localization stage.</span></span>

[<span data-ttu-id="c6507-112">Локализация</span><span class="sxs-lookup"><span data-stu-id="c6507-112">Localization</span></span>](localization.md)

<span data-ttu-id="c6507-113">Этот этап включает настройку приложения для конкретных языков или регионов.</span><span class="sxs-lookup"><span data-stu-id="c6507-113">This step involves customizing an application for specific cultures or regions.</span></span> <span data-ttu-id="c6507-114">Если этапы глобализации и анализа локализуемости были проведены правильно, то локализация заключается главным образом в переводе пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c6507-114">If the globalization and localizability steps have been performed correctly, localization consists primarily of translating the user interface.</span></span>

<span data-ttu-id="c6507-115">Выполнение этих трех этапов обеспечивает два преимущества:</span><span class="sxs-lookup"><span data-stu-id="c6507-115">Following these three steps provides two advantages:</span></span>

- <span data-ttu-id="c6507-116">Освобождает от необходимости модифицировать приложение, разработанное для поддержки одного языка и региона, например английского языка (США), чтобы обеспечить поддержку дополнительных языков и регионов.</span><span class="sxs-lookup"><span data-stu-id="c6507-116">It frees you from having to retrofit an application that is designed to support a single culture, such as U.S. English, to support additional cultures.</span></span>

- <span data-ttu-id="c6507-117">В результате создаются локализованные приложения, которые более стабильны и содержат меньше ошибок.</span><span class="sxs-lookup"><span data-stu-id="c6507-117">It results in localized applications that are more stable and have fewer bugs.</span></span>

<span data-ttu-id="c6507-118">Платформа .NET предоставляет широкие возможности для разработки международных и локализованных приложений.</span><span class="sxs-lookup"><span data-stu-id="c6507-118">.NET provides extensive support for the development of world-ready and localized applications.</span></span> <span data-ttu-id="c6507-119">В частности, многие элементы типов в библиотеке классов .NET упрощают глобализацию, возвращая значения, отражающие соглашения языка и региональных параметров текущего либо заданного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c6507-119">In particular, many type members in the .NET class library aid globalization by returning values that reflect the conventions of either the current user's culture or a specified culture.</span></span> <span data-ttu-id="c6507-120">Кроме того, платформа .NET поддерживает вспомогательные сборки, ускоряющие процесс локализации приложений.</span><span class="sxs-lookup"><span data-stu-id="c6507-120">Also, .NET supports satellite assemblies, which facilitate the process of localizing an application.</span></span>

<span data-ttu-id="c6507-121">Дополнительные сведения см. в [документации по глобализации](/globalization/).</span><span class="sxs-lookup"><span data-stu-id="c6507-121">For additional information, see the [Globalization documentation](/globalization/).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c6507-122">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c6507-122">In this section</span></span>

[<span data-ttu-id="c6507-123">Глобализация</span><span class="sxs-lookup"><span data-stu-id="c6507-123">Globalization</span></span>](globalization.md)

<span data-ttu-id="c6507-124">Описание первого этапа создания международного приложения, который предполагает проектирование и кодирование приложения, не зависящего от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c6507-124">Discusses the first stage of creating a world-ready application, which involves designing and coding an application that is culture-neutral and language-neutral.</span></span>

[<span data-ttu-id="c6507-125">Проверка локализуемости</span><span class="sxs-lookup"><span data-stu-id="c6507-125">Localizability review</span></span>](localizability-review.md)

<span data-ttu-id="c6507-126">Описание второго этапа создания международного приложения, который предполагает выявление потенциальных препятствий для локализации.</span><span class="sxs-lookup"><span data-stu-id="c6507-126">Discusses the second stage of creating a localized application, which involves identifying potential roadblocks to localization.</span></span>

[<span data-ttu-id="c6507-127">Локализация</span><span class="sxs-lookup"><span data-stu-id="c6507-127">Localization</span></span>](localization.md)

<span data-ttu-id="c6507-128">Описание заключительного этапа создания локализованного приложения, который предполагает настройку пользовательского интерфейса приложения для конкретных регионов или языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c6507-128">Discusses the final stage of creating a localized application, which involves customizing an application's user interface for specific regions or cultures.</span></span>

[<span data-ttu-id="c6507-129">Операции со строками без учета языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="c6507-129">Culture-insensitive string operations</span></span>](culture-insensitive-string-operations.md)

<span data-ttu-id="c6507-130">Статья описывает, как использовать методы и классы .NET, которые по умолчанию учитывают язык и региональные параметры, для получения результатов без их учета.</span><span class="sxs-lookup"><span data-stu-id="c6507-130">Describes how to use .NET methods and classes that are culture-sensitive by default to obtain culture-insensitive results.</span></span>

[<span data-ttu-id="c6507-131">Рекомендации по разработке международных приложений</span><span class="sxs-lookup"><span data-stu-id="c6507-131">Best practices for developing world-ready applications</span></span>](best-practices-for-developing-world-ready-apps.md)

<span data-ttu-id="c6507-132">Описание лучших методик по глобализации, локализации и разработке международных приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c6507-132">Describes the best practices to follow for globalization, localization, and developing world-ready ASP.NET applications.</span></span>

## <a name="reference"></a><span data-ttu-id="c6507-133">Справочник</span><span class="sxs-lookup"><span data-stu-id="c6507-133">Reference</span></span>

- <span data-ttu-id="c6507-134">Пространство имен <xref:System.Globalization?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c6507-134"><xref:System.Globalization?displayProperty=nameWithType> namespace</span></span>

   <span data-ttu-id="c6507-135">Содержит классы, определяющие сведения, относящиеся к языку и региональным параметрам, такие как язык, страна или регион, используемые календари, шаблоны форматирования дат, денежных единиц и чисел, а также порядок сортировки строк.</span><span class="sxs-lookup"><span data-stu-id="c6507-135">Contains classes that define culture-related information, including the language, the country/region, the calendars in use, the format patterns for dates, currency, and numbers, and the sort order for strings.</span></span>

- <span data-ttu-id="c6507-136">Пространство имен <xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="c6507-136"><xref:System.Resources> namespace</span></span>

   <span data-ttu-id="c6507-137">Предоставляет классы для создания и использования ресурсов, а также управления ими.</span><span class="sxs-lookup"><span data-stu-id="c6507-137">Provides classes for creating, manipulating, and using resources.</span></span>

- <span data-ttu-id="c6507-138">Пространство имен <xref:System.Text></span><span class="sxs-lookup"><span data-stu-id="c6507-138"><xref:System.Text> namespace</span></span>

   <span data-ttu-id="c6507-139">Содержит классы, представляющие ASCII, ANSI, Юникод и другие форматы кодировки символов.</span><span class="sxs-lookup"><span data-stu-id="c6507-139">Contains classes representing ASCII, ANSI, Unicode, and other character encodings.</span></span>

- [<span data-ttu-id="c6507-140">Resgen.exe (генератор файлов ресурсов)</span><span class="sxs-lookup"><span data-stu-id="c6507-140">Resgen.exe (Resource File Generator)</span></span>](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)

   <span data-ttu-id="c6507-141">Описание использования программы Resgen.exe для преобразования файлов .txt и .resx и файлов формата XML (.resx) в двоичные файлы .resources общей среды исполнения.</span><span class="sxs-lookup"><span data-stu-id="c6507-141">Describes how to use Resgen.exe to convert .txt files and XML-based resource format (.resx) files to common language runtime binary .resources files.</span></span>

- [<span data-ttu-id="c6507-142">Winres.exe (редактор ресурсов Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c6507-142">Winres.exe (Windows Forms Resource Editor)</span></span>](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)

   <span data-ttu-id="c6507-143">Описание использования Winres.exe для локализации форм Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c6507-143">Describes how to use Winres.exe to localize Windows Forms forms.</span></span>
