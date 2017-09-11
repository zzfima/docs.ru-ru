---
title: "Использование структур (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 67fa4f764e6e40041e4b8e37eccbd1adb2b509d3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="ac937-102">Использование структур (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ac937-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="ac937-103">Тип `struct` подходит для представления простых объектов, таких как `Point`, `Rectangle`и `Color`.</span><span class="sxs-lookup"><span data-stu-id="ac937-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="ac937-104">Хотя point удобно представить в виде [класса](../../../csharp/language-reference/keywords/class.md) с [автоматически реализуемыми свойствами](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), в некоторых сценариях [структура](../../../csharp/language-reference/keywords/struct.md) может оказаться более эффективной.</span><span class="sxs-lookup"><span data-stu-id="ac937-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="ac937-105">Например, при объявлении массива из 1000 объектов `Point` потребуется выделить дополнительную память для ссылки на каждый объект. В этом случае использование структуры будет более экономичным вариантом.</span><span class="sxs-lookup"><span data-stu-id="ac937-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="ac937-106">Поскольку [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] содержит объект с именем <xref:System.Drawing.Point>, структура в этом примере называется CoOrds.</span><span class="sxs-lookup"><span data-stu-id="ac937-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "CoOrds" instead.</span></span>  
  
 <span data-ttu-id="ac937-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ac937-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="ac937-108">Определение конструктора по умолчанию (без параметров) для структуры является ошибочным.</span><span class="sxs-lookup"><span data-stu-id="ac937-108">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="ac937-109">Кроме того, ошибкой будет и инициализация поля экземпляра в основной части структуры.</span><span class="sxs-lookup"><span data-stu-id="ac937-109">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="ac937-110">Члены структуры можно инициализировать только с помощью параметризованного конструктора или путем доступа к членам по отдельности после объявления структуры.</span><span class="sxs-lookup"><span data-stu-id="ac937-110">You can initialize struct members only by using a parameterized constructor or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="ac937-111">Любые закрытые или иным образом недоступные члены можно инициализировать только в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="ac937-111">Any private or otherwise inaccessible members can be initialized only in a constructor.</span></span>  
  
 <span data-ttu-id="ac937-112">При создании объекта структуры с помощью оператора [new](../../../csharp/language-reference/keywords/new.md) также вызывается соответствующий конструктор.</span><span class="sxs-lookup"><span data-stu-id="ac937-112">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called.</span></span> <span data-ttu-id="ac937-113">В отличие от классов, создавать структуры можно без оператора `new` .</span><span class="sxs-lookup"><span data-stu-id="ac937-113">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="ac937-114">В этом случае вызов конструктора не выполняется, что способствует более эффективному выделению ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ac937-114">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="ac937-115">Однако поля остаются незназначенными и объект нельзя использовать до инициализации всех полей.</span><span class="sxs-lookup"><span data-stu-id="ac937-115">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span>  
  
 <span data-ttu-id="ac937-116">Если структура содержит ссылочный тип в качестве члена, конструктор по умолчанию члена необходимо вызывать явным образом. В противном случае член останется неназначенными и структуру использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="ac937-116">When a struct contains a reference type as a member, the default constructor of the member must be invoked explicitly, otherwise the member remains unassigned and the struct cannot be used.</span></span> <span data-ttu-id="ac937-117">(Это приводит к ошибке компилятора CS0171.)</span><span class="sxs-lookup"><span data-stu-id="ac937-117">(This results in compiler error CS0171.)</span></span>  
  
 <span data-ttu-id="ac937-118">В отличие от классов, структуры не поддерживают наследование.</span><span class="sxs-lookup"><span data-stu-id="ac937-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="ac937-119">Структура не может наследовать от другой структуры или класса и не может быть базовой для класса.</span><span class="sxs-lookup"><span data-stu-id="ac937-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="ac937-120">Однако структуры наследуют от базового класса <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ac937-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="ac937-121">Структуры могут реализовывать интерфейсы именно так, как это делают классы.</span><span class="sxs-lookup"><span data-stu-id="ac937-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="ac937-122">Нельзя объявить класс с помощью ключевого слова `struct`.</span><span class="sxs-lookup"><span data-stu-id="ac937-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="ac937-123">В C# классы и структуры имеют разную семантику.</span><span class="sxs-lookup"><span data-stu-id="ac937-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="ac937-124">Структура является типом значения, а класс — ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="ac937-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="ac937-125">Дополнительные сведения см. в разделе [Типы значений](../../../csharp/language-reference/keywords/value-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac937-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="ac937-126">Если не требуется использовать семантику ссылочного типа, система может более эффективно обрабатывать небольшой класс, объявленный как структура.</span><span class="sxs-lookup"><span data-stu-id="ac937-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="ac937-127">Пример 1</span><span class="sxs-lookup"><span data-stu-id="ac937-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="ac937-128">Описание</span><span class="sxs-lookup"><span data-stu-id="ac937-128">Description</span></span>  
 <span data-ttu-id="ac937-129">В этом примере показана инициализация `struct` с использованием конструктора по умолчанию и параметризованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="ac937-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ac937-130">Код</span><span class="sxs-lookup"><span data-stu-id="ac937-130">Code</span></span>  
 <span data-ttu-id="ac937-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ac937-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="ac937-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ac937-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="ac937-133">Пример 2</span><span class="sxs-lookup"><span data-stu-id="ac937-133">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="ac937-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ac937-134">Description</span></span>  
 <span data-ttu-id="ac937-135">В этом примере демонстрируется уникальная возможность структур.</span><span class="sxs-lookup"><span data-stu-id="ac937-135">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="ac937-136">Здесь создается объект CoOrds без использования оператора `new` .</span><span class="sxs-lookup"><span data-stu-id="ac937-136">It creates a CoOrds object without using the `new` operator.</span></span> <span data-ttu-id="ac937-137">Если заменить слово `struct` на слово `class`, программа не будет скомпилирована.</span><span class="sxs-lookup"><span data-stu-id="ac937-137">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ac937-138">Код</span><span class="sxs-lookup"><span data-stu-id="ac937-138">Code</span></span>  
 <span data-ttu-id="ac937-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ac937-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="ac937-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ac937-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac937-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ac937-141">See Also</span></span>  
 <span data-ttu-id="ac937-142">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac937-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ac937-143">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac937-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="ac937-144">Структуры</span><span class="sxs-lookup"><span data-stu-id="ac937-144">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

