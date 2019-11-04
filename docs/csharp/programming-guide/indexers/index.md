---
title: Руководство по программированию на C#. Индексаторы
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: 02dc8c21b86438c801fb151d9f02a223b60d6197
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423234"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="6f06c-102">Индексаторы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="6f06c-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="6f06c-103">Индексаторы позволяют индексировать экземпляры класса или структуры точно так же, как и массивы.</span><span class="sxs-lookup"><span data-stu-id="6f06c-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="6f06c-104">Индексированное значение можно задавать или получать без явного указания типа или экземпляра элемента.</span><span class="sxs-lookup"><span data-stu-id="6f06c-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="6f06c-105">Индексаторы действуют как [свойства](../classes-and-structs/properties.md), за исключением того, что их акцессоры принимают параметры.</span><span class="sxs-lookup"><span data-stu-id="6f06c-105">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="6f06c-106">В следующем примере определяется универсальный класс с простыми акцессорами [get](../../language-reference/keywords/get.md) и [set](../../language-reference/keywords/set.md) для назначения и получения значений.</span><span class="sxs-lookup"><span data-stu-id="6f06c-106">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="6f06c-107">Класс `Program` создает экземпляр этого класса для хранения строк.</span><span class="sxs-lookup"><span data-stu-id="6f06c-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="6f06c-108">Дополнительные примеры см. в разделе [Связанные разделы](./index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="6f06c-108">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="6f06c-109">Определения текста выражений</span><span class="sxs-lookup"><span data-stu-id="6f06c-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="6f06c-110">Довольно часто акцессор get или set индексатора состоит из одной инструкции, которая просто возвращает или задает значение.</span><span class="sxs-lookup"><span data-stu-id="6f06c-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="6f06c-111">Члены, воплощающие выражение, предоставляют упрощенный синтаксис для поддержки такого варианта использования.</span><span class="sxs-lookup"><span data-stu-id="6f06c-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="6f06c-112">Начиная с версии C# 6, доступные только для чтения индексаторы можно реализовать в виде члена, воплощающего выражение, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6f06c-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="6f06c-113">Обратите внимание, что `=>` представляет тело выражения, а ключевое слово `get` не используется.</span><span class="sxs-lookup"><span data-stu-id="6f06c-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="6f06c-114">Начиная с версии C# 7.0, методы доступа get и set можно реализовывать в виде членов с телом в виде выражения.</span><span class="sxs-lookup"><span data-stu-id="6f06c-114">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="6f06c-115">В этом случае необходимо указывать оба ключевых слова (`get` и `set`).</span><span class="sxs-lookup"><span data-stu-id="6f06c-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="6f06c-116">Например:</span><span class="sxs-lookup"><span data-stu-id="6f06c-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="6f06c-117">Общие сведения об индексаторах</span><span class="sxs-lookup"><span data-stu-id="6f06c-117">Indexers Overview</span></span>  
  
- <span data-ttu-id="6f06c-118">Индексаторы позволяют индексировать объекты так же, как и массивы.</span><span class="sxs-lookup"><span data-stu-id="6f06c-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="6f06c-119">Метод доступа `get` возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="6f06c-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="6f06c-120">Метод доступа `set` назначает значение.</span><span class="sxs-lookup"><span data-stu-id="6f06c-120">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="6f06c-121">Ключевое слово [this](../../language-reference/keywords/this.md) используется для определения индексаторов.</span><span class="sxs-lookup"><span data-stu-id="6f06c-121">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="6f06c-122">Ключевое слово [value`set` используется для определения значения, присваиваемого индексатором ](../../language-reference/keywords/value.md).</span><span class="sxs-lookup"><span data-stu-id="6f06c-122">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
- <span data-ttu-id="6f06c-123">Индексаторы не нужно индексировать по целому значению; пользователь может определить конкретный механизм поиска на свое усмотрение.</span><span class="sxs-lookup"><span data-stu-id="6f06c-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="6f06c-124">Индексаторы могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="6f06c-124">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="6f06c-125">Индексаторы могут иметь более одного формального параметра, например при доступе к двумерному массиву.</span><span class="sxs-lookup"><span data-stu-id="6f06c-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="BKMK_RelatedSections"></a> <span data-ttu-id="6f06c-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6f06c-126">Related Sections</span></span>  
  
- [<span data-ttu-id="6f06c-127">Использование индексаторов</span><span class="sxs-lookup"><span data-stu-id="6f06c-127">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="6f06c-128">Индексаторы в интерфейсах</span><span class="sxs-lookup"><span data-stu-id="6f06c-128">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="6f06c-129">Сравнение свойств и индексаторов</span><span class="sxs-lookup"><span data-stu-id="6f06c-129">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="6f06c-130">Ограничение доступности методов доступа</span><span class="sxs-lookup"><span data-stu-id="6f06c-130">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="6f06c-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6f06c-131">C# Language Specification</span></span>  

<span data-ttu-id="6f06c-132">Дополнительные сведения см. в разделе [Индексаторы](~/_csharplang/spec/classes.md#indexers) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="6f06c-132">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="6f06c-133">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="6f06c-133">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f06c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="6f06c-134">See also</span></span>

- [<span data-ttu-id="6f06c-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6f06c-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6f06c-136">Свойства</span><span class="sxs-lookup"><span data-stu-id="6f06c-136">Properties</span></span>](../classes-and-structs/properties.md)
