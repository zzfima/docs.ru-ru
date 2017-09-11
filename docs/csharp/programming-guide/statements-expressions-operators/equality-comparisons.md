---
title: "Сравнения на равенство (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object equality [C#]
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
caps.latest.revision: 14
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
ms.openlocfilehash: 948bbc1b5b8535cc31ea362497fa69a816b43edc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="equality-comparisons-c-programming-guide"></a><span data-ttu-id="363cf-102">Сравнения на равенство (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="363cf-102">Equality Comparisons (C# Programming Guide)</span></span>
<span data-ttu-id="363cf-103">Иногда возникает необходимость проверить равенство двух значений.</span><span class="sxs-lookup"><span data-stu-id="363cf-103">It is sometimes necessary to compare two values for equality.</span></span> <span data-ttu-id="363cf-104">В некоторых случаях проверяется *равенство значений*, которое также называют их *эквивалентностью*, что означает, что содержащиеся в двух переменных значения равны.</span><span class="sxs-lookup"><span data-stu-id="363cf-104">In some cases, you are testing for *value equality*, also known as *equivalence*, which means that the values that are contained by the two variables are equal.</span></span> <span data-ttu-id="363cf-105">В других случаях требуется определить, ссылаются ли две переменные на один и тот же объект в памяти.</span><span class="sxs-lookup"><span data-stu-id="363cf-105">In other cases, you have to determine whether two variables refer to the same underlying object in memory.</span></span> <span data-ttu-id="363cf-106">Такой тип равенства называется *равенством ссылок* или *идентичностью*.</span><span class="sxs-lookup"><span data-stu-id="363cf-106">This type of equality is called *reference equality*, or *identity*.</span></span> <span data-ttu-id="363cf-107">В этом разделе описаны эти два типа равенства и приведены ссылки на разделы, содержащие дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="363cf-107">This topic describes these two kinds of equality and provides links to other topics for more information.</span></span>  
  
## <a name="reference-equality"></a><span data-ttu-id="363cf-108">Равенство ссылок</span><span class="sxs-lookup"><span data-stu-id="363cf-108">Reference Equality</span></span>  
 <span data-ttu-id="363cf-109">Равенство ссылок означает, что два объекта ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="363cf-109">Reference equality means that two object references refer to the same underlying object.</span></span> <span data-ttu-id="363cf-110">Это может произойти при простом присваивании, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="363cf-110">This can occur through simple assignment, as shown in the following example.</span></span>  
  
 <span data-ttu-id="363cf-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="363cf-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span></span>  
  
 <span data-ttu-id="363cf-112">В этом фрагменте кода создается два объекта, но после инструкции присваивания они оба ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="363cf-112">In this code, two objects are created, but after the assignment statement, both references refer to the same object.</span></span> <span data-ttu-id="363cf-113">Поэтому между ними устанавливается равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="363cf-113">Therefore they have reference equality.</span></span> <span data-ttu-id="363cf-114">Метод <xref:System.Object.ReferenceEquals%2A> позволяет определить, ссылаются ли две ссылки на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="363cf-114">Use the <xref:System.Object.ReferenceEquals%2A> method to determine whether two references refer to the same object.</span></span>  
  
 <span data-ttu-id="363cf-115">Концепция равенства ссылок применима только к ссылочным типам.</span><span class="sxs-lookup"><span data-stu-id="363cf-115">The concept of reference equality applies only to reference types.</span></span> <span data-ttu-id="363cf-116">Объекты типа значения не могут иметь равенство ссылок, поскольку переменной присваивается экземпляр типа значения, создается копия этого значения.</span><span class="sxs-lookup"><span data-stu-id="363cf-116">Value type objects cannot have reference equality because when an instance of a value type is assigned to a variable, a copy of the value is made.</span></span> <span data-ttu-id="363cf-117">Поэтому две распакованные структуры никогда не могут ссылаться на одно и то же расположение в памяти.</span><span class="sxs-lookup"><span data-stu-id="363cf-117">Therefore you can never have two unboxed structs that refer to the same location in memory.</span></span> <span data-ttu-id="363cf-118">Более того, для сравнения двух типов значений <xref:System.Object.ReferenceEquals%2A> всегда будет возвращаться результат `false`, даже если содержащиеся в объектах значения идентичны.</span><span class="sxs-lookup"><span data-stu-id="363cf-118">Furthermore, if you use <xref:System.Object.ReferenceEquals%2A> to compare two value types, the result will always be `false`, even if the values that are contained in the objects are all identical.</span></span> <span data-ttu-id="363cf-119">Это связано с тем, что каждая переменная запакована в отдельный экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="363cf-119">This is because each variable is boxed into a separate object instance.</span></span> <span data-ttu-id="363cf-120">Дополнительные сведения см. в разделе [Практическое руководство. Тестирование на равенство (идентичность) ссылок](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span><span class="sxs-lookup"><span data-stu-id="363cf-120">For more information, see [How to: Test for Reference Equality (Identity)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span></span>  
  
## <a name="value-equality"></a><span data-ttu-id="363cf-121">равенство значений</span><span class="sxs-lookup"><span data-stu-id="363cf-121">Value Equality</span></span>  
 <span data-ttu-id="363cf-122">Равенство значений означает, что два объекта содержат одинаковое значение или одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="363cf-122">Value equality means that two objects contain the same value or values.</span></span> <span data-ttu-id="363cf-123">Для примитивных типов значений, таких как [int](../../../csharp/language-reference/keywords/int.md) или [bool](../../../csharp/language-reference/keywords/bool.md), проверка на равенство значений представляет собой очевидную задачу.</span><span class="sxs-lookup"><span data-stu-id="363cf-123">For primitive value types such as [int](../../../csharp/language-reference/keywords/int.md) or [bool](../../../csharp/language-reference/keywords/bool.md), tests for value equality are straightforward.</span></span> <span data-ttu-id="363cf-124">Можно использовать оператор [==](../../../csharp/language-reference/operators/equality-comparison-operator.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="363cf-124">You can use the [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) operator, as shown in the following example.</span></span>  
  
```csharp  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.   
if( b == a)   
{  
    // The two integers are equal.  
}  
```  
  
 <span data-ttu-id="363cf-125">Для большинства других типов проверка равенства значений является более сложной, поскольку при этом необходимо понимать, как равенство определено в типе.</span><span class="sxs-lookup"><span data-stu-id="363cf-125">For most other types, testing for value equality is more complex because it requires that you understand how the type defines it.</span></span> <span data-ttu-id="363cf-126">Для всех классов и структур, имеющих несколько полей или свойств, равенство значений часто определяется как равенство значений всех полей и свойств.</span><span class="sxs-lookup"><span data-stu-id="363cf-126">For classes and structs that have multiple fields or properties, value equality is often defined to mean that all fields or properties have the same value.</span></span> <span data-ttu-id="363cf-127">Например, два объекта `Point` могут быть определены как равные, если значение pointA.X равняется pointB.X, а значение pointA.Y равняется pointB.Y.</span><span class="sxs-lookup"><span data-stu-id="363cf-127">For example, two `Point` objects might be defined to be equivalent if pointA.X is equal to pointB.X and pointA.Y is equal to pointB.Y.</span></span>  
  
 <span data-ttu-id="363cf-128">Однако общего требования о том, что равенство должно определяться на основе всех полей в типе, нет.</span><span class="sxs-lookup"><span data-stu-id="363cf-128">However, there is no requirement that equivalence be based on all the fields in a type.</span></span> <span data-ttu-id="363cf-129">Оно может определяться и на основе части полей.</span><span class="sxs-lookup"><span data-stu-id="363cf-129">It can be based on a subset.</span></span> <span data-ttu-id="363cf-130">При сравнении значений типов сторонних разработчиков необходимо понимать, как именно реализовано равенство для таких типов.</span><span class="sxs-lookup"><span data-stu-id="363cf-130">When you compare types that you do not own, you should make sure to understand specifically how equivalence is defined for that type.</span></span> <span data-ttu-id="363cf-131">Для получения дополнительных сведений об определении равенства значений в собственных классах и структурах см. [Практическое руководство. Определение равенства значений для типа](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span><span class="sxs-lookup"><span data-stu-id="363cf-131">For more information about how to define value equality in your own classes and structs, see [How to: Define Value Equality for a Type](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span></span>  
  
### <a name="value-equality-for-floating-point-values"></a><span data-ttu-id="363cf-132">Равенство значений с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="363cf-132">Value Equality for Floating Point Values</span></span>  
 <span data-ttu-id="363cf-133">Проверка равенства значений с плавающей запятой ([double](../../../csharp/language-reference/keywords/double.md) и [float](../../../csharp/language-reference/keywords/float.md)) представляет проблему из-за неточности арифметических операций с плавающей запятой на двоичных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="363cf-133">Equality comparisons of floating point values ([double](../../../csharp/language-reference/keywords/double.md) and [float](../../../csharp/language-reference/keywords/float.md)) are problematic because of the imprecision of floating point arithmetic on binary computers.</span></span> <span data-ttu-id="363cf-134">Дополнительные сведения можно найти в заметках в разделе <xref:System.Double?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="363cf-134">For more information, see the remarks in the topic <xref:System.Double?displayProperty=fullName>.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="363cf-135">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="363cf-135">Related Topics</span></span>  
  
|<span data-ttu-id="363cf-136">Заголовок</span><span class="sxs-lookup"><span data-stu-id="363cf-136">Title</span></span>|<span data-ttu-id="363cf-137">Описание</span><span class="sxs-lookup"><span data-stu-id="363cf-137">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="363cf-138">Практическое руководство. Проверка на ссылочное равенство (идентичность)</span><span class="sxs-lookup"><span data-stu-id="363cf-138">How to: Test for Reference Equality (Identity)</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)|<span data-ttu-id="363cf-139">Описание процедуры проверки равенства ссылок двух переменных.</span><span class="sxs-lookup"><span data-stu-id="363cf-139">Describes how to determine whether two variables have reference equality.</span></span>|  
|[<span data-ttu-id="363cf-140">Практическое руководство. Определение равенства значений для типа</span><span class="sxs-lookup"><span data-stu-id="363cf-140">How to: Define Value Equality for a Type</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)|<span data-ttu-id="363cf-141">Описание предоставления пользовательского определения равенства значений для типа.</span><span class="sxs-lookup"><span data-stu-id="363cf-141">Describes how to provide a custom definition of value equality for a type.</span></span>|  
|[<span data-ttu-id="363cf-142">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="363cf-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)|<span data-ttu-id="363cf-143">Ссылки на подробные сведения о важных элементах языка C#, а также об элементах, доступных в этом языке благодаря .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="363cf-143">Provides links to detailed information about important C# language features and features that are available to C# through the .NET Framework.</span></span>|  
|[<span data-ttu-id="363cf-144">Типы</span><span class="sxs-lookup"><span data-stu-id="363cf-144">Types</span></span>](../../../csharp/programming-guide/types/index.md)|<span data-ttu-id="363cf-145">Сведения о системе типов C# и ссылки на дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="363cf-145">Provides information about the C# type system and links to additional information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="363cf-146">См. также</span><span class="sxs-lookup"><span data-stu-id="363cf-146">See Also</span></span>  
 [<span data-ttu-id="363cf-147">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="363cf-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

