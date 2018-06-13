---
title: Оператор new (Справочник по C#)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 2ba3c574897ae5f1ec66e3810e23f0af74bd8872
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268925"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="f8b46-102">Оператор new (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f8b46-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="f8b46-103">Применяется для создания объектов и вызова конструкторов.</span><span class="sxs-lookup"><span data-stu-id="f8b46-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="f8b46-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8b46-104">For example:</span></span>  
  
```csharp
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="f8b46-105">Он также используется для создания экземпляров анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="f8b46-105">It is also used to create instances of anonymous types:</span></span>  
  
```csharp
var query = from cust in customers  
            select new { Name = cust.Name, Address = cust.PrimaryAddress };  
```  
  
 <span data-ttu-id="f8b46-106">С помощью оператора `new` можно вызвать заданный по умолчанию конструктор для типов значений.</span><span class="sxs-lookup"><span data-stu-id="f8b46-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="f8b46-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8b46-107">For example:</span></span>  
  
```csharp
int i = new int();  
```  
  
 <span data-ttu-id="f8b46-108">В предыдущем операторе `i` инициализируется значением `0`, которое является значением по умолчанию для типа `int`.</span><span class="sxs-lookup"><span data-stu-id="f8b46-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="f8b46-109">Этот оператор приводит к результату, представленному далее.</span><span class="sxs-lookup"><span data-stu-id="f8b46-109">The statement has the same effect as the following:</span></span>  
  
```csharp
int i = 0;  
```  
  
 <span data-ttu-id="f8b46-110">Полный список значений по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="f8b46-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="f8b46-111">Следует помнить, что объявление конструктора по умолчанию для [структуры](../../../csharp/language-reference/keywords/struct.md) является ошибкой, поскольку каждый тип значения неявно имеет открытый заданный по умолчанию конструктор.</span><span class="sxs-lookup"><span data-stu-id="f8b46-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="f8b46-112">Можно объявить параметризованные конструкторы в типе структуры, чтобы задать начальные значения, однако это необходимо, только если требуются значения, отличные от установленных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f8b46-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="f8b46-113">И объекты типа значения, такие как структуры, и объекты ссылочного типа, такие как классы, уничтожаются автоматически, но объекты типа значения уничтожаются при уничтожении содержащего их контекста, в то время как объекты ссылочного типа уничтожаются сборщиком мусора через неопределенное время после удаления последней ссылки на них.</span><span class="sxs-lookup"><span data-stu-id="f8b46-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="f8b46-114">Для типов, которые содержат ресурсы, такие как дескрипторы файлов или сетевые подключения, желательно использовать детерминированную очистку, чтобы как можно скорее высвободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f8b46-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="f8b46-115">Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f8b46-115">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="f8b46-116">Оператор `new` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="f8b46-116">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="f8b46-117">Если оператору `new` не удается выделить память, он создает исключение <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="f8b46-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b46-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f8b46-118">Example</span></span>  
 <span data-ttu-id="f8b46-119">В следующем примере создаются объект `struct` и объект класса, которые инициализируются с помощью оператора `new`, после чего им присваиваются значения.</span><span class="sxs-lookup"><span data-stu-id="f8b46-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="f8b46-120">Отображаются заданные по умолчанию и присвоенные значения.</span><span class="sxs-lookup"><span data-stu-id="f8b46-120">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="f8b46-121">Обратите внимание, что в примере строка имеет значение по умолчанию `null`.</span><span class="sxs-lookup"><span data-stu-id="f8b46-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="f8b46-122">Поэтому она не отображается.</span><span class="sxs-lookup"><span data-stu-id="f8b46-122">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f8b46-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f8b46-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8b46-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f8b46-124">See Also</span></span>  
 [<span data-ttu-id="f8b46-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f8b46-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f8b46-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f8b46-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f8b46-127">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f8b46-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f8b46-128">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="f8b46-128">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="f8b46-129">new</span><span class="sxs-lookup"><span data-stu-id="f8b46-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="f8b46-130">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f8b46-130">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
