---
title: Оператор new (справочник по C#)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 362217b247bd2ab7a2eec2f86cbaaf1a0652a3ad
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706480"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="e204a-102">Оператор new (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e204a-102">new operator (C# Reference)</span></span>

<span data-ttu-id="e204a-103">Применяется для создания объектов и вызова конструкторов.</span><span class="sxs-lookup"><span data-stu-id="e204a-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="e204a-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="e204a-104">For example:</span></span>

```csharp
Class1 obj  = new Class1();
```

<span data-ttu-id="e204a-105">Он также используется для создания экземпляров анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="e204a-105">It is also used to create instances of anonymous types:</span></span>

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

<span data-ttu-id="e204a-106">С помощью оператора `new` можно вызвать заданный по умолчанию конструктор для типов значений.</span><span class="sxs-lookup"><span data-stu-id="e204a-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="e204a-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="e204a-107">For example:</span></span>

```csharp
int i = new int();
```

<span data-ttu-id="e204a-108">В предыдущем операторе `i` инициализируется значением `0`, которое является значением по умолчанию для типа `int`.</span><span class="sxs-lookup"><span data-stu-id="e204a-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="e204a-109">Этот оператор приводит к результату, представленному далее.</span><span class="sxs-lookup"><span data-stu-id="e204a-109">The statement has the same effect as the following:</span></span>

```csharp
int i = 0;
```

<span data-ttu-id="e204a-110">Полный список значений по умолчанию см. в разделе [Таблица значений по умолчанию](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e204a-110">For a complete list of default values, see [Default Values Table](default-values-table.md).</span></span>

<span data-ttu-id="e204a-111">Следует помнить, что объявление конструктора по умолчанию для [структуры](struct.md) является ошибкой, поскольку каждый тип значения неявно имеет открытый заданный по умолчанию конструктор.</span><span class="sxs-lookup"><span data-stu-id="e204a-111">Remember that it is an error to declare a default constructor for a [struct](struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="e204a-112">Можно объявить параметризованные конструкторы в типе структуры, чтобы задать начальные значения, однако это необходимо, только если требуются значения, отличные от установленных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e204a-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>

<span data-ttu-id="e204a-113">И объекты типа значения, такие как структуры, и объекты ссылочного типа, такие как классы, уничтожаются автоматически, но объекты типа значения уничтожаются при уничтожении содержащего их контекста, в то время как объекты ссылочного типа уничтожаются сборщиком мусора через неопределенное время после удаления последней ссылки на них.</span><span class="sxs-lookup"><span data-stu-id="e204a-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="e204a-114">Для типов, которые содержат ресурсы, такие как дескрипторы файлов или сетевые подключения, желательно использовать детерминированную очистку, чтобы как можно скорее высвободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="e204a-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="e204a-115">Дополнительные сведения см. в разделе [Оператор using](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e204a-115">For more information, see [using Statement](using-statement.md).</span></span>

<span data-ttu-id="e204a-116">Оператор `new` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="e204a-116">The `new` operator cannot be overloaded.</span></span>

<span data-ttu-id="e204a-117">Если оператору `new` не удается выделить память, он создает исключение <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="e204a-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="e204a-118">Пример</span><span class="sxs-lookup"><span data-stu-id="e204a-118">Example</span></span>

<span data-ttu-id="e204a-119">В следующем примере создаются объект `struct` и объект класса, которые инициализируются с помощью оператора `new`, после чего им присваиваются значения.</span><span class="sxs-lookup"><span data-stu-id="e204a-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="e204a-120">Отображаются заданные по умолчанию и присвоенные значения.</span><span class="sxs-lookup"><span data-stu-id="e204a-120">The default and the assigned values are displayed.</span></span>

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

<span data-ttu-id="e204a-121">Обратите внимание, что в примере строка имеет значение по умолчанию `null`.</span><span class="sxs-lookup"><span data-stu-id="e204a-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="e204a-122">Поэтому она не отображается.</span><span class="sxs-lookup"><span data-stu-id="e204a-122">Therefore, it is not displayed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e204a-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e204a-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e204a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e204a-124">See also</span></span>

- [<span data-ttu-id="e204a-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e204a-125">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="e204a-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e204a-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e204a-127">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e204a-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e204a-128">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="e204a-128">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="e204a-129">new</span><span class="sxs-lookup"><span data-stu-id="e204a-129">new</span></span>](new.md)
- [<span data-ttu-id="e204a-130">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="e204a-130">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)