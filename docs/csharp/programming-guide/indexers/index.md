---
title: "Индексаторы (Руководство по программированию в C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: 784308f3073114cd0c07cf15edae527a2654edec
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="c600c-102">Индексаторы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="c600c-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="c600c-103">Индексаторы позволяют индексировать экземпляры класса или структуры точно так же, как и массивы.</span><span class="sxs-lookup"><span data-stu-id="c600c-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="c600c-104">Индексированное значение можно задавать или получать без явного указания типа или экземпляра элемента.</span><span class="sxs-lookup"><span data-stu-id="c600c-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="c600c-105">Индексаторы действуют как [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), за исключением того, что их акцессоры принимают параметры.</span><span class="sxs-lookup"><span data-stu-id="c600c-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="c600c-106">В следующем примере определяется универсальный класс с простыми акцессорами [get](../../../csharp/language-reference/keywords/get.md) и [set](../../../csharp/language-reference/keywords/set.md) для назначения и получения значений.</span><span class="sxs-lookup"><span data-stu-id="c600c-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="c600c-107">Класс `Program` создает экземпляр этого класса для хранения строк.</span><span class="sxs-lookup"><span data-stu-id="c600c-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 <span data-ttu-id="c600c-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c600c-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c600c-109">Дополнительные примеры см. в разделе [Связанные разделы](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="c600c-109">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="c600c-110">Определения текста выражений</span><span class="sxs-lookup"><span data-stu-id="c600c-110">Expression Body Definitions</span></span>  
 
<span data-ttu-id="c600c-111">Довольно часто акцессор get или set индексатора состоит из одной инструкции, которая просто возвращает или задает значение.</span><span class="sxs-lookup"><span data-stu-id="c600c-111">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="c600c-112">Члены, воплощающие выражение, предоставляют упрощенный синтаксис для поддержки такого варианта использования.</span><span class="sxs-lookup"><span data-stu-id="c600c-112">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="c600c-113">Начиная с версии C# 6, доступные только для чтения индексаторы можно реализовать в виде члена, воплощающего выражение, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c600c-113">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

<span data-ttu-id="c600c-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c600c-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span></span>  

<span data-ttu-id="c600c-115">Обратите внимание, что `=>` представляет тело выражения, а ключевое слово `get` не используется.</span><span class="sxs-lookup"><span data-stu-id="c600c-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="c600c-116">Начиная с версии C# 7, акцессоры get и set можно реализовывать в виде членов, воплощающих выражение.</span><span class="sxs-lookup"><span data-stu-id="c600c-116">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="c600c-117">В этом случае необходимо указывать оба ключевых слова (`get` и `set`).</span><span class="sxs-lookup"><span data-stu-id="c600c-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="c600c-118">Например:</span><span class="sxs-lookup"><span data-stu-id="c600c-118">For example:</span></span>

<span data-ttu-id="c600c-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c600c-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span></span>  
  
## <a name="indexers-overview"></a><span data-ttu-id="c600c-120">Общие сведения об индексаторах</span><span class="sxs-lookup"><span data-stu-id="c600c-120">Indexers Overview</span></span>  
  
-   <span data-ttu-id="c600c-121">Индексаторы позволяют индексировать объекты так же, как и массивы.</span><span class="sxs-lookup"><span data-stu-id="c600c-121">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="c600c-122">Метод доступа `get` возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="c600c-122">A `get` accessor returns a value.</span></span> <span data-ttu-id="c600c-123">Метод доступа `set` назначает значение.</span><span class="sxs-lookup"><span data-stu-id="c600c-123">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="c600c-124">Ключевое слово [this](../../../csharp/language-reference/keywords/this.md) используется для определения индексаторов.</span><span class="sxs-lookup"><span data-stu-id="c600c-124">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="c600c-125">Ключевое слово [value`set` используется для определения значения, присваиваемого индексатором ](../../../csharp/language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="c600c-125">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="c600c-126">Индексаторы не нужно индексировать по целому значению; пользователь может определить конкретный механизм поиска на свое усмотрение.</span><span class="sxs-lookup"><span data-stu-id="c600c-126">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="c600c-127">Индексаторы могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="c600c-127">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="c600c-128">Индексаторы могут иметь более одного формального параметра, например при доступе к двумерному массиву.</span><span class="sxs-lookup"><span data-stu-id="c600c-128">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <span data-ttu-id="c600c-129"><a name="BKMK_RelatedSections"></a> Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c600c-129"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="c600c-130">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="c600c-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="c600c-131">Индексаторы в интерфейсах</span><span class="sxs-lookup"><span data-stu-id="c600c-131">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="c600c-132">Сравнение свойств и индексаторов</span><span class="sxs-lookup"><span data-stu-id="c600c-132">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="c600c-133">Ограничение доступности методов доступа</span><span class="sxs-lookup"><span data-stu-id="c600c-133">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="c600c-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c600c-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c600c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c600c-135">See Also</span></span>  
 <span data-ttu-id="c600c-136">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c600c-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c600c-137">Свойства</span><span class="sxs-lookup"><span data-stu-id="c600c-137">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

