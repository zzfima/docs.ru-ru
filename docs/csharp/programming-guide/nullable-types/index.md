---
title: "Типы, допускающие значения NULL (Руководство по программированию на C#)"
ms.date: 05/15/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9b874b265f4adb131a056ea1ef6fb5ffc820343f
ms.sourcegitcommit: 75a180acb5d8a2dbd4a52915ce8e980749fb1d05
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="f08d3-102">Типы, допускающие значения NULL (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f08d3-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="f08d3-103">Типы, допускающие значения NULL, являются экземплярами структуры <xref:System.Nullable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f08d3-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="f08d3-104">Тип, допускающий значение NULL, может принимать такой же диапазон значений, как и его базовый тип значения, а также дополнительное значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="f08d3-105">Например, для типа `Nullable<Int32>` (Int32, допускающий значения NULL) можно назначить любое значение в диапазоне от -2147483648 до 2147483647 или значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="f08d3-106">Тип `Nullable<bool>` может иметь значения [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), или [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="f08d3-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="f08d3-107">Возможность назначения `null` для числовых и логических типов особенно полезна при работе с базами данных и другими источниками данных, которые могут содержать элементы без присвоенного значения.</span><span class="sxs-lookup"><span data-stu-id="f08d3-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="f08d3-108">Например, логическое поле в базе данных может хранить значения `true` или `false`, или может быть неопределенным.</span><span class="sxs-lookup"><span data-stu-id="f08d3-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
<span data-ttu-id="f08d3-109">Дополнительные примеры см. в разделе [Using Nullable Types (C# Programming Guide)](../../../csharp/programming-guide/nullable-types/using-nullable-types.md) (Руководство по программированию на C#. Использование типов, допускающих значение NULL)</span><span class="sxs-lookup"><span data-stu-id="f08d3-109">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="f08d3-110">Обзор типов, допускающих значения NULL</span><span class="sxs-lookup"><span data-stu-id="f08d3-110">Nullable Types Overview</span></span>  
 <span data-ttu-id="f08d3-111">Типы, допускающие значения NULL, имеют следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="f08d3-111">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="f08d3-112">Типы, допускающие значение NULL, представляют переменные типа значения, которым может быть назначено значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-112">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="f08d3-113">Нельзя создать тип, допускающий значение NULL, на основе ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="f08d3-113">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="f08d3-114">(Ссылочные типы всегда поддерживают значение `null`.)</span><span class="sxs-lookup"><span data-stu-id="f08d3-114">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="f08d3-115">Синтаксис `T?` является сокращением для <xref:System.Nullable%601>, где `T` является типом значения.</span><span class="sxs-lookup"><span data-stu-id="f08d3-115">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="f08d3-116">Эти две формы записи являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="f08d3-116">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="f08d3-117">Типу, допускающему значение NULL, можно присвоить значение так же, как и обычному типу значения, например `int? x = 10;` или `double? d = 4.108`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-117">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="f08d3-118">Также типу, допускающему значение NULL, может быть присвоено значение `null`: `int? x = null.`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-118">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="f08d3-119">Используйте метод <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType>, чтобы возвращать либо присвоенное значение, либо значение по умолчанию для базового типа, если значение равно `null`, например так: `int j = x.GetValueOrDefault();`</span><span class="sxs-lookup"><span data-stu-id="f08d3-119">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="f08d3-120">Используйте доступные только для чтения свойства <xref:System.Nullable%601.HasValue%2A> и <xref:System.Nullable%601.Value%2A> для проверки на NULL и получения значения, как показано в следующем примере: `if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="f08d3-120">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="f08d3-121">Свойство `HasValue` возвращает `true`, если переменная содержит допустимое значение, или `false`, если она имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-121">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="f08d3-122">Свойство `Value` возвращает значение, если оно назначено.</span><span class="sxs-lookup"><span data-stu-id="f08d3-122">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="f08d3-123">В противном случае возникает исключение <xref:System.InvalidOperationException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f08d3-123">Otherwise, a <xref:System.InvalidOperationException?displayProperty=nameWithType> is thrown.</span></span>  
  
    -   <span data-ttu-id="f08d3-124">По умолчанию для объекта `HasValue` установлено значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-124">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="f08d3-125">Свойство `Value` не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f08d3-125">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="f08d3-126">Вы также можете использовать с типом, допускающим значение NULL, операторы `==` и `!=`, как показано в следующем примере: `if (x != null) y = x;`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-126">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="f08d3-127">Используйте оператор `??`, чтобы назначить значение по умолчанию, которое будет применяться в том случае, если тип, допускающий значение NULL, имеет значение `null` и присваивается типу, не допускающему значение NULL (например, `int? x = null; int y = x ?? -1;`).</span><span class="sxs-lookup"><span data-stu-id="f08d3-127">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="f08d3-128">Нельзя создавать вложенные типы, допускающие значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f08d3-128">Nested nullable types are not allowed.</span></span> <span data-ttu-id="f08d3-129">Этот код компилироваться не будет: `Nullable<Nullable<int>> n;`.</span><span class="sxs-lookup"><span data-stu-id="f08d3-129">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f08d3-130">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f08d3-130">Related Sections</span></span>  
 <span data-ttu-id="f08d3-131">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f08d3-131">For more information:</span></span>  
  
-   [<span data-ttu-id="f08d3-132">Использование допускающих значение NULL типов</span><span class="sxs-lookup"><span data-stu-id="f08d3-132">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="f08d3-133">Упаковка-преобразование типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="f08d3-133">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="f08d3-134">?? Оператор</span><span class="sxs-lookup"><span data-stu-id="f08d3-134">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f08d3-135">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f08d3-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f08d3-136">См. также</span><span class="sxs-lookup"><span data-stu-id="f08d3-136">See Also</span></span>  
 <xref:System.Nullable>  
 [<span data-ttu-id="f08d3-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f08d3-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f08d3-138">C#</span><span class="sxs-lookup"><span data-stu-id="f08d3-138">C#</span></span>](../../../csharp/index.md)  
 [<span data-ttu-id="f08d3-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="f08d3-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 <span data-ttu-id="f08d3-140">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Что означает термин "расширенные"?)</span><span class="sxs-lookup"><span data-stu-id="f08d3-140">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)</span></span>
