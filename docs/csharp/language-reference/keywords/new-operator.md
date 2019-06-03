---
title: Справочник по C#. Оператор new
ms.custom: seodec18
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 409a5307eaacd2eac865e2882cc7228521260dbe
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421871"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="0b27f-102">Оператор new (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0b27f-102">new operator (C# Reference)</span></span>

<span data-ttu-id="0b27f-103">Применяется для создания объектов и вызова конструкторов.</span><span class="sxs-lookup"><span data-stu-id="0b27f-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="0b27f-104">Например:</span><span class="sxs-lookup"><span data-stu-id="0b27f-104">For example:</span></span>

```csharp
Class1 obj  = new Class1();
```

<span data-ttu-id="0b27f-105">Он также используется для создания экземпляров анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="0b27f-105">It is also used to create instances of anonymous types:</span></span>

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

<span data-ttu-id="0b27f-106">Оператор `new` также используется для вызова конструктора без параметров для типов значений.</span><span class="sxs-lookup"><span data-stu-id="0b27f-106">The `new` operator is also used to invoke the parameterless constructor for value types.</span></span> <span data-ttu-id="0b27f-107">Например:</span><span class="sxs-lookup"><span data-stu-id="0b27f-107">For example:</span></span>

```csharp
int i = new int();
```

<span data-ttu-id="0b27f-108">В предыдущем операторе `i` инициализируется значением `0`, которое является значением по умолчанию для типа `int`.</span><span class="sxs-lookup"><span data-stu-id="0b27f-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="0b27f-109">Этот оператор приводит к результату, представленному далее.</span><span class="sxs-lookup"><span data-stu-id="0b27f-109">The statement has the same effect as the following:</span></span>

```csharp
int i = 0;
```

<span data-ttu-id="0b27f-110">Полный список значений по умолчанию см. в разделе [Таблица значений по умолчанию](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0b27f-110">For a complete list of default values, see [Default Values Table](default-values-table.md).</span></span>

<span data-ttu-id="0b27f-111">Помните, что ошибкой было бы объявить конструктор без параметров для [структуры](struct.md), так как каждый тип значения неявно имеет открытый конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="0b27f-111">Remember that it is an error to declare a parameterless constructor for a [struct](struct.md) because every value type implicitly has a public parameterless constructor.</span></span> <span data-ttu-id="0b27f-112">Можно объявить параметризованные конструкторы в типе структуры, чтобы задать начальные значения, однако это необходимо, только если требуются значения, отличные от установленных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b27f-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>

<span data-ttu-id="0b27f-113">И объекты типа значения, такие как структуры, и объекты ссылочного типа, такие как классы, уничтожаются автоматически, но объекты типа значения уничтожаются при уничтожении содержащего их контекста, в то время как объекты ссылочного типа уничтожаются сборщиком мусора через неопределенное время после удаления последней ссылки на них.</span><span class="sxs-lookup"><span data-stu-id="0b27f-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="0b27f-114">Для типов, которые содержат ресурсы, такие как дескрипторы файлов или сетевые подключения, желательно использовать детерминированную очистку, чтобы как можно скорее высвободить эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="0b27f-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="0b27f-115">Дополнительные сведения см. в разделе [Оператор using](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0b27f-115">For more information, see [using Statement](using-statement.md).</span></span>

<span data-ttu-id="0b27f-116">Оператор `new` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="0b27f-116">The `new` operator cannot be overloaded.</span></span>

<span data-ttu-id="0b27f-117">Если оператору `new` не удается выделить память, он создает исключение <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="0b27f-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="0b27f-118">Пример</span><span class="sxs-lookup"><span data-stu-id="0b27f-118">Example</span></span>

<span data-ttu-id="0b27f-119">В следующем примере создаются объект `struct` и объект класса, которые инициализируются с помощью оператора `new`, после чего им присваиваются значения.</span><span class="sxs-lookup"><span data-stu-id="0b27f-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="0b27f-120">Отображаются заданные по умолчанию и присвоенные значения.</span><span class="sxs-lookup"><span data-stu-id="0b27f-120">The default and the assigned values are displayed.</span></span>

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

<span data-ttu-id="0b27f-121">Обратите внимание, что в примере строка имеет значение по умолчанию `null`.</span><span class="sxs-lookup"><span data-stu-id="0b27f-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="0b27f-122">Поэтому она не отображается.</span><span class="sxs-lookup"><span data-stu-id="0b27f-122">Therefore, it is not displayed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b27f-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0b27f-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0b27f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0b27f-124">See also</span></span>

- [<span data-ttu-id="0b27f-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0b27f-125">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="0b27f-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0b27f-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0b27f-127">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0b27f-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0b27f-128">new</span><span class="sxs-lookup"><span data-stu-id="0b27f-128">new</span></span>](new.md)
- [<span data-ttu-id="0b27f-129">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="0b27f-129">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
