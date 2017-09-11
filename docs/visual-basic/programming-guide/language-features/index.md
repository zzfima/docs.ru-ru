---
title: "Возможности и элементы языка Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, elements of
- Visual Basic code
ms.assetid: b0b21730-298c-47e6-9a2f-cc81f628067b
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3594e6622e8bc76839a15739a31ad27d17de8455
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="visual-basic-language-features"></a><span data-ttu-id="f94b2-102">Возможности и элементы языка Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f94b2-102">Visual Basic Language Features</span></span>
<span data-ttu-id="f94b2-103">В следующих разделах описываются и обсуждаются основные компоненты объектно-ориентированного языка программирования [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f94b2-103">The following topics introduce and discuss the essential components of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], an object-oriented programming language.</span></span> <span data-ttu-id="f94b2-104">После того, как вы подготовите пользовательский интерфейс для вашего приложения с помощью форм и элементов управления, необходимо написать код, определяющий поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="f94b2-104">After creating the user interface for your application using forms and controls, you need to write the code that defines the application's behavior.</span></span> <span data-ttu-id="f94b2-105">Как и любой современный язык программирования, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] поддерживает несколько привычных программных конструкций и элементов языка.</span><span class="sxs-lookup"><span data-stu-id="f94b2-105">As with any modern programming language, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supports a number of common programming constructs and language elements.</span></span>  
  
 <span data-ttu-id="f94b2-106">Если у вас есть опыт программирования на других языках, большая часть материала этой статьи покажется вам знакомой.</span><span class="sxs-lookup"><span data-stu-id="f94b2-106">If you have programmed in other languages, much of the material covered in this section might seem familiar.</span></span> <span data-ttu-id="f94b2-107">Большинство конструкций похожи на те, что вы встречаются в других языках, но ориентированность [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] на события диктует некоторые незначительные отличия.</span><span class="sxs-lookup"><span data-stu-id="f94b2-107">While most of the constructs are similar to those in other languages, the event-driven nature of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] introduces some subtle differences.</span></span>  
  
 <span data-ttu-id="f94b2-108">Если вы пока новичок в программировании, материал этой статьи поможет вам понять основные принципы создания кода.</span><span class="sxs-lookup"><span data-stu-id="f94b2-108">If you are new to programming, the material in this section serves as an introduction to the basic building blocks for writing code.</span></span> <span data-ttu-id="f94b2-109">Хорошо разобравшись с основами, вы сразу сможете создавать мощные приложения на [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f94b2-109">Once you understand the basics, you can create powerful applications using [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f94b2-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="f94b2-110">In This Section</span></span>  
 [<span data-ttu-id="f94b2-111">Массивы</span><span class="sxs-lookup"><span data-stu-id="f94b2-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="f94b2-112">Описывает возможность сделать код более компактным и мощным, объявляя и используя массивы с несколькими связанными значениями.</span><span class="sxs-lookup"><span data-stu-id="f94b2-112">Discusses making your code more compact and powerful by declaring and using arrays, which hold multiple related values.</span></span>  
  
 [<span data-ttu-id="f94b2-113">Инициализаторы коллекций</span><span class="sxs-lookup"><span data-stu-id="f94b2-113">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 <span data-ttu-id="f94b2-114">Описывает инициализаторы коллекций, которые позволяют создать коллекцию и заполнить ее начальным набором значений.</span><span class="sxs-lookup"><span data-stu-id="f94b2-114">Describes collection initializers, which enable you to create a collection and populate it with an initial set of values.</span></span>  
  
 [<span data-ttu-id="f94b2-115">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="f94b2-115">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 <span data-ttu-id="f94b2-116">Описывает хранение неизменных значений для многократного использования, в том числе наборов связанных констант.</span><span class="sxs-lookup"><span data-stu-id="f94b2-116">Discusses storing unchanging values for repeated use, including sets of related constant values.</span></span>  
  
 [<span data-ttu-id="f94b2-117">Поток управления</span><span class="sxs-lookup"><span data-stu-id="f94b2-117">Control Flow</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 <span data-ttu-id="f94b2-118">Демонстрирует управление потоком выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="f94b2-118">Shows how to regulate the flow of your program's execution.</span></span>  
  
 [<span data-ttu-id="f94b2-119">Типы данных</span><span class="sxs-lookup"><span data-stu-id="f94b2-119">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="f94b2-120">Описывает, какие виды данных может содержать элемент программирования, и как хранятся эти данные.</span><span class="sxs-lookup"><span data-stu-id="f94b2-120">Describes what kinds of data a programming element can hold and how that data is stored.</span></span>  
  
 [<span data-ttu-id="f94b2-121">Объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="f94b2-121">Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 <span data-ttu-id="f94b2-122">Описывает элементы программирования, которые вы можете объявить, в том числе имена, характеристики и действия компилятора для разрешения ссылок на них.</span><span class="sxs-lookup"><span data-stu-id="f94b2-122">Covers programming elements you can declare, their names and characteristics, and how the compiler resolves references to them.</span></span>  
  
 [<span data-ttu-id="f94b2-123">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f94b2-123">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 <span data-ttu-id="f94b2-124">Дает вводную информацию о делегатах и их применении в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f94b2-124">Provides an introduction to delegates and how they are used in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f94b2-125">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="f94b2-125">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 <span data-ttu-id="f94b2-126">Описывает связывание, которое выполняется компилятором при присвоении объекта переменной объекта, а также различия между объектами с ранним и поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="f94b2-126">Describes binding, which is performed by the compiler when an object is assigned to an object variable, and the differences between early-bound and late-bound objects.</span></span>  
  
 [<span data-ttu-id="f94b2-127">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="f94b2-127">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 <span data-ttu-id="f94b2-128">Дает общий обзор синтаксических ошибок, ошибок времени выполнения и логических ошибок.</span><span class="sxs-lookup"><span data-stu-id="f94b2-128">Provides an overview of syntax errors, run-time errors, and logic errors.</span></span>  
  
 [<span data-ttu-id="f94b2-129">События</span><span class="sxs-lookup"><span data-stu-id="f94b2-129">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 <span data-ttu-id="f94b2-130">Демонстрирует объявление и использование событий.</span><span class="sxs-lookup"><span data-stu-id="f94b2-130">Shows how to declare and use events.</span></span>  
  
 [<span data-ttu-id="f94b2-131">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f94b2-131">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 <span data-ttu-id="f94b2-132">Описывает, что такое интерфейсы и как их можно использовать в приложениях.</span><span class="sxs-lookup"><span data-stu-id="f94b2-132">Describes what interfaces are and how you can use them in your applications.</span></span>  
  
 [<span data-ttu-id="f94b2-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="f94b2-133">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="f94b2-134">Содержит ссылки на разделы, описывающие возможности [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] и его использование в программах.</span><span class="sxs-lookup"><span data-stu-id="f94b2-134">Provides links to topics that introduce [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] features and programming.</span></span>  
  
 [<span data-ttu-id="f94b2-135">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="f94b2-135">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 <span data-ttu-id="f94b2-136">Описывает объекты и классы, методы их использования и взаимоотношения, а также предоставляемые ими свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="f94b2-136">Provides an overview of objects and classes, how they are used, their relationships to each other, and the properties, methods, and events they expose.</span></span>  
  
 [<span data-ttu-id="f94b2-137">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="f94b2-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 <span data-ttu-id="f94b2-138">Описывает элементы кода, которые управляют элементами хранения значений, предлагает методы их эффективного использования и объединения для получения новых значений.</span><span class="sxs-lookup"><span data-stu-id="f94b2-138">Describes the code elements that manipulate value-holding elements, how to use them efficiently, and how to combine them to yield new values.</span></span>  
  
 [<span data-ttu-id="f94b2-139">Процедуры</span><span class="sxs-lookup"><span data-stu-id="f94b2-139">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 <span data-ttu-id="f94b2-140">Описывает процедуры `Sub`, `Function`, `Property` и `Operator`, а также сложные варианты их использования, например рекурсивные и перегруженные процедуры.</span><span class="sxs-lookup"><span data-stu-id="f94b2-140">Describes `Sub`, `Function`, `Property`, and `Operator` procedures, as well as advanced topics such as recursive and overloaded procedures.</span></span>  
  
 [<span data-ttu-id="f94b2-141">Операторы</span><span class="sxs-lookup"><span data-stu-id="f94b2-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 <span data-ttu-id="f94b2-142">Описывает операторы объявления и исполняемые операторы.</span><span class="sxs-lookup"><span data-stu-id="f94b2-142">Describes declaration and executable statements.</span></span>  
  
 [<span data-ttu-id="f94b2-143">Строки</span><span class="sxs-lookup"><span data-stu-id="f94b2-143">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 <span data-ttu-id="f94b2-144">Содержит ссылки на разделы, описывающие основные принципы использования строк в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f94b2-144">Provides links to topics that describe the basic concepts about using strings in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f94b2-145">Переменные</span><span class="sxs-lookup"><span data-stu-id="f94b2-145">Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/index.md)  
 <span data-ttu-id="f94b2-146">Описывает переменные и их использование в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f94b2-146">Introduces variables and describes how to use them in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f94b2-147">XML</span><span class="sxs-lookup"><span data-stu-id="f94b2-147">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="f94b2-148">Содержит ссылки на разделы, описывающие использование XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f94b2-148">Provides links to topics that describe how to use XML in Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f94b2-149">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f94b2-149">Related Sections</span></span>  
 [<span data-ttu-id="f94b2-150">Коллекции</span><span class="sxs-lookup"><span data-stu-id="f94b2-150">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 <span data-ttu-id="f94b2-151">Описывает некоторые типы коллекций, предоставляемых платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f94b2-151">Describes some of the types of collections that are provided by the .NET Framework.</span></span> <span data-ttu-id="f94b2-152">Демонстрирует использование простых коллекций и коллекций с парами "ключ — значение".</span><span class="sxs-lookup"><span data-stu-id="f94b2-152">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>  
  
 [<span data-ttu-id="f94b2-153">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f94b2-153">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 <span data-ttu-id="f94b2-154">Содержит справочные сведения о различных аспектах программирования на [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f94b2-154">Provides reference information on various aspects of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming.</span></span>

