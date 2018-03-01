---
title: "Оператор new (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3c2b484b9872a54ce42520de77a723b9edb441a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="a3503-102">Оператор new (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a3503-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="a3503-103">Применяется для создания объектов и вызова конструкторов.</span><span class="sxs-lookup"><span data-stu-id="a3503-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="a3503-104">Например:</span><span class="sxs-lookup"><span data-stu-id="a3503-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="a3503-105">Он также используется для создания экземпляров анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="a3503-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="a3503-106">С помощью оператора `new` можно вызвать заданный по умолчанию конструктор для типов значений.</span><span class="sxs-lookup"><span data-stu-id="a3503-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="a3503-107">Например:</span><span class="sxs-lookup"><span data-stu-id="a3503-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="a3503-108">В предыдущем операторе `i` инициализируется значением `0`, которое является значением по умолчанию для типа `int`.</span><span class="sxs-lookup"><span data-stu-id="a3503-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="a3503-109">Этот оператор приводит к результату, представленному далее.</span><span class="sxs-lookup"><span data-stu-id="a3503-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="a3503-110">Полный список значений по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="a3503-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="a3503-111">Следует помнить, что объявление конструктора по умолчанию для [структуры](../../../csharp/language-reference/keywords/struct.md) является ошибкой, поскольку каждый тип значения неявно имеет открытый заданный по умолчанию конструктор.</span><span class="sxs-lookup"><span data-stu-id="a3503-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="a3503-112">Можно объявить параметризованные конструкторы в типе структуры, чтобы задать начальные значения, однако это необходимо, только если требуются значения, отличные от установленных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a3503-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="a3503-113">Объекты типа значения, например структуры, создаются в стеке, тогда как объекты ссылочного типа, например классы, создаются в куче.</span><span class="sxs-lookup"><span data-stu-id="a3503-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="a3503-114">Уничтожение обоих типов объектов выполняется автоматически, но объекты на основе типов значений удаляются при выходе за рамки области действия, а объекты на основе ссылочных типов — в неуказанное время после удаления последней ссылки, указывающей на них.</span><span class="sxs-lookup"><span data-stu-id="a3503-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="a3503-115">Для ссылочных типов, использующих фиксированные ресурсы, например большой объем памяти, файловые дескрипторы, сетевые подключения, иногда рекомендуется использовать детерминированную финализацию для обеспечения скорейшего уничтожения объекта.</span><span class="sxs-lookup"><span data-stu-id="a3503-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="a3503-116">Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a3503-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="a3503-117">Оператор `new` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="a3503-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="a3503-118">Если оператору `new` не удается выделить память, он создает исключение <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="a3503-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3503-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a3503-119">Example</span></span>  
 <span data-ttu-id="a3503-120">В следующем примере создаются объект `struct` и объект класса, которые инициализируются с помощью оператора `new`, после чего им присваиваются значения.</span><span class="sxs-lookup"><span data-stu-id="a3503-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="a3503-121">Отображаются заданные по умолчанию и присвоенные значения.</span><span class="sxs-lookup"><span data-stu-id="a3503-121">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="a3503-122">Обратите внимание, что в примере строка имеет значение по умолчанию `null`.</span><span class="sxs-lookup"><span data-stu-id="a3503-122">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="a3503-123">Поэтому она не отображается.</span><span class="sxs-lookup"><span data-stu-id="a3503-123">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a3503-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a3503-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3503-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a3503-125">See Also</span></span>  
 [<span data-ttu-id="a3503-126">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a3503-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a3503-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a3503-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a3503-128">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a3503-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a3503-129">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="a3503-129">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="a3503-130">new</span><span class="sxs-lookup"><span data-stu-id="a3503-130">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="a3503-131">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="a3503-131">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
