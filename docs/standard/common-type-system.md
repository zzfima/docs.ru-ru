---
title: "Система общих типов CTS и спецификация CLS"
description: "Сведения о том, как система общих типов (CTS) и спецификация CLS позволяют .NET поддерживать несколько языков."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3b1f5725-ac94-4f17-8e5f-244442438a4d
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7626b0a6a902465416187b2c09d624dfe9a9773
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="common-type-system--common-language-specification"></a><span data-ttu-id="88b34-104">Система общих типов CTS и спецификация CLS</span><span class="sxs-lookup"><span data-stu-id="88b34-104">Common Type System & Common Language Specification</span></span>

<span data-ttu-id="88b34-105">Два этих термина широко распространены в среде .NET и чрезвычайно важны для понимания того, как реализация .NET позволяет осуществлять разработку на нескольких языках и как все это работает.</span><span class="sxs-lookup"><span data-stu-id="88b34-105">Again, two terms that are freely used in the .NET world, they actually are crucial to understand how a .NET implementation enables multi-language development and to understand how it works.</span></span>

## <a name="common-type-system"></a><span data-ttu-id="88b34-106">Система общих типов CTS</span><span class="sxs-lookup"><span data-stu-id="88b34-106">Common Type System</span></span>

<span data-ttu-id="88b34-107">Для начала напомним, что реализация .NET является _независимой от языка_.</span><span class="sxs-lookup"><span data-stu-id="88b34-107">To start from the beginning, remember that a .NET implementation is _language agnostic_.</span></span> <span data-ttu-id="88b34-108">Это не просто означает, что программист может писать код на любом языке, который можно скомпилировать в промежуточный язык.</span><span class="sxs-lookup"><span data-stu-id="88b34-108">This doesn’t just mean that a programmer can write her code in any language that can be compiled to IL.</span></span> <span data-ttu-id="88b34-109">Это также означает, что ему нужно взаимодействовать с кодом, написанным на других языках, которые поддерживаются в реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="88b34-109">It also means that she needs to be able to interact with code written in other languages that are able to be used on a .NET implementation.</span></span>

<span data-ttu-id="88b34-110">Чтобы сделать это без каких-либо затруднений, требуется способ описания всех поддерживаемых типов.</span><span class="sxs-lookup"><span data-stu-id="88b34-110">In order to do this transparently, there has to be a common way to describe all supported types.</span></span> <span data-ttu-id="88b34-111">Именно за это и отвечает система общих типов CTS.</span><span class="sxs-lookup"><span data-stu-id="88b34-111">This is what the Common Type System (CTS) is in charge of doing.</span></span> <span data-ttu-id="88b34-112">Она предназначена для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="88b34-112">It was made to do several things:</span></span>

*   <span data-ttu-id="88b34-113">Создание платформы для выполнения на разных языках.</span><span class="sxs-lookup"><span data-stu-id="88b34-113">Establish a framework for cross-language execution.</span></span>
*   <span data-ttu-id="88b34-114">Предоставление объектно-ориентированной модели для поддержки реализации различных языков в реализации .NET.</span><span class="sxs-lookup"><span data-stu-id="88b34-114">Provide an object-oriented model to support implementing various languages on a .NET implementation.</span></span>
*   <span data-ttu-id="88b34-115">Определение набора правил, которым должны следовать все языки при работе с типами.</span><span class="sxs-lookup"><span data-stu-id="88b34-115">Define a set of rules that all languages must follow when it comes to working with types.</span></span>
*   <span data-ttu-id="88b34-116">Предоставление библиотеки, которая содержит базовые типы-примитивы, используемые при разработке приложений (например, `Boolean`, `Byte`, `Char` и т. д.).</span><span class="sxs-lookup"><span data-stu-id="88b34-116">Provide a library that contains the basic primitive types that are used in application development (such as, `Boolean`, `Byte`, `Char` etc.)</span></span>

<span data-ttu-id="88b34-117">Система CTS определяет две разновидности типов, которые должны поддерживаться: типы значений и ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="88b34-117">CTS defines two main kinds of types that should be supported: reference and value types.</span></span> <span data-ttu-id="88b34-118">Имена разновидностей указывают на их определения.</span><span class="sxs-lookup"><span data-stu-id="88b34-118">Their names point to their definitions.</span></span>

<span data-ttu-id="88b34-119">Объекты ссылочных типов представлены ссылкой на фактическое значение объекта. Здесь ссылка аналогична указателю в C/C++.</span><span class="sxs-lookup"><span data-stu-id="88b34-119">Reference types’ objects are represented by a reference to the object’s actual value; a reference here is similar to a pointer in C/C++.</span></span> <span data-ttu-id="88b34-120">Она просто указывает на адрес памяти, где находятся значения объектов.</span><span class="sxs-lookup"><span data-stu-id="88b34-120">It simply refers to a memory location where the objects’ values are.</span></span> <span data-ttu-id="88b34-121">Это оказывает значительное влияние на способ использования этих типов.</span><span class="sxs-lookup"><span data-stu-id="88b34-121">This has a profound impact on how these types are used.</span></span> <span data-ttu-id="88b34-122">Если назначить ссылочный тип переменной, а затем передать эту переменную, например, в метод, любые изменения объекта будут отражены на основном объекте. Копирование при этом не выполняется.</span><span class="sxs-lookup"><span data-stu-id="88b34-122">If you assign a reference type to a variable and then pass that variable into a method, for instance, any changes to the object will be reflected on the main object; there is no copying.</span></span>

<span data-ttu-id="88b34-123">В типах значений объекты, наоборот, представлены своими значениями.</span><span class="sxs-lookup"><span data-stu-id="88b34-123">Value types are the opposite, where the objects are represented by their values.</span></span> <span data-ttu-id="88b34-124">Назначение типа значения переменной, по сути, равнозначно копированию значения этого объекта.</span><span class="sxs-lookup"><span data-stu-id="88b34-124">If you assign a value type to a variable, you are essentially copying a value of the object.</span></span>

<span data-ttu-id="88b34-125">Система CTS определяет несколько категорий типов, каждый из которых имеет собственную семантику и способ использования:</span><span class="sxs-lookup"><span data-stu-id="88b34-125">CTS defines several categories of types, each with their specific semantics and usage:</span></span>

*   <span data-ttu-id="88b34-126">Классы</span><span class="sxs-lookup"><span data-stu-id="88b34-126">Classes</span></span>
*   <span data-ttu-id="88b34-127">Структуры</span><span class="sxs-lookup"><span data-stu-id="88b34-127">Structures</span></span>
*   <span data-ttu-id="88b34-128">перечислениям;</span><span class="sxs-lookup"><span data-stu-id="88b34-128">Enums</span></span>
*   <span data-ttu-id="88b34-129">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="88b34-129">Interfaces</span></span>
*   <span data-ttu-id="88b34-130">Делегаты</span><span class="sxs-lookup"><span data-stu-id="88b34-130">Delegates</span></span>

<span data-ttu-id="88b34-131">Система CTS также определяет все другие свойства типов, такие как модификаторы доступа, которые являются допустимыми членами типа, порядок наследования и перегрузки и т. п.</span><span class="sxs-lookup"><span data-stu-id="88b34-131">CTS also defines all other properties of the types, such as access modifiers, what are valid type members, how inheritance and overloading works and so on.</span></span> <span data-ttu-id="88b34-132">К сожалению, детальное рассмотрение этих аспектов выходит за рамки данной вводной статьи, но вы можете обратиться к разделу [Дополнительные ресурсы](#more-resources) в конце статьи, где приведены ссылки на более подробные материалы по этой теме.</span><span class="sxs-lookup"><span data-stu-id="88b34-132">Unfortunately, going deep into any of those is beyond the scope of an introductory article such as this, but you can consult [More resources](#more-resources) section at the end for links to more in-depth content that covers these topics.</span></span>

## <a name="common-language-specification"></a><span data-ttu-id="88b34-133">Спецификация CLS</span><span class="sxs-lookup"><span data-stu-id="88b34-133">Common Language Specification</span></span>

<span data-ttu-id="88b34-134">Чтобы реализовать сценарии полного взаимодействия, все создаваемые в коде объекты должны основываться на чем-то общем в тех языках, которые используют (_вызывают_) их.</span><span class="sxs-lookup"><span data-stu-id="88b34-134">To enable full interoperability scenarios, all objects that are created in code must rely on some commonality in the languages that are consuming them (are their _callers_).</span></span> <span data-ttu-id="88b34-135">Так как существует множество различных языков, .NET описывает такие общие черты в так называемой **спецификации CLS**.</span><span class="sxs-lookup"><span data-stu-id="88b34-135">Since there are numerous different languages, .NET has specified those commonalities in something called the **Common Language Specification** (CLS).</span></span> <span data-ttu-id="88b34-136">Спецификация CLS определяет набор функций, необходимых многим распространенным приложениям.</span><span class="sxs-lookup"><span data-stu-id="88b34-136">CLS defines a set of features that are needed by many common applications.</span></span> <span data-ttu-id="88b34-137">Она также предоставляет своего рода перечень компонентов, которые должен поддерживать любой язык, реализуемый на базе .NET.</span><span class="sxs-lookup"><span data-stu-id="88b34-137">It also provides a sort of recipe for any language that is implemented on top of .NET on what it needs to support.</span></span>

<span data-ttu-id="88b34-138">Спецификация CLS является подмножеством системы CTS.</span><span class="sxs-lookup"><span data-stu-id="88b34-138">CLS is a subset of the CTS.</span></span> <span data-ttu-id="88b34-139">Это означает, что все правила в CTS применяются и к CLS, если только в CLS не действуют более строгие правила.</span><span class="sxs-lookup"><span data-stu-id="88b34-139">This means that all of the rules in the CTS also apply to the CLS, unless the CLS rules are more strict.</span></span> <span data-ttu-id="88b34-140">Если компонент создается с использованием только правил CLS, то есть предоставляет в своем API только функции CLS, он считается **CLS-совместимым**.</span><span class="sxs-lookup"><span data-stu-id="88b34-140">If a component is built using only the rules in the CLS, that is, it exposes only the CLS features in its API, it is said to be **CLS-compliant**.</span></span> <span data-ttu-id="88b34-141">Например, `<framework-librares>` являются CLS-совместимыми, так как они должны работать во всех языках, поддерживаемых в .NET.</span><span class="sxs-lookup"><span data-stu-id="88b34-141">For instance, the `<framework-librares>` are CLS-compliant precisely because they need to work across all of the languages that are supported on .NET.</span></span>

<span data-ttu-id="88b34-142">Для получения общих сведений обо всех функциях CLS см. документы в приведенном ниже разделе [Дополнительные ресурсы](#more-resources).</span><span class="sxs-lookup"><span data-stu-id="88b34-142">You can consult the documents in the [More Resources](#more-resources) section below to get an overview of all the features in the CLS.</span></span>

## <a name="more-resources"></a><span data-ttu-id="88b34-143">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="88b34-143">More resources</span></span>

*   [<span data-ttu-id="88b34-144">Система общих типов CTS</span><span class="sxs-lookup"><span data-stu-id="88b34-144">Common Type System</span></span>](./base-types/common-type-system.md)
*   [<span data-ttu-id="88b34-145">Спецификация CLS</span><span class="sxs-lookup"><span data-stu-id="88b34-145">Common Language Specification</span></span>](language-independence-and-language-independent-components.md)
