---
title: "out (универсальный модификатор) (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: 15
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
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: a560a0307723d32750a7e26ad4ee1afec360a849
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="e58a5-102">out (универсальный модификатор) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e58a5-102">out (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="e58a5-103">Для параметров универсального типа ключевое слово `out` указывает, что параметр типа является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="e58a5-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="e58a5-104">Ключевое слово `out` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="e58a5-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="e58a5-105">Ковариация позволяет использовать производные типы со степенью наследования больше, нежели у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="e58a5-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="e58a5-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="e58a5-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="e58a5-107">Ковариация и контравариантность поддерживаются для ссылочных типов, но не для типов значений.</span><span class="sxs-lookup"><span data-stu-id="e58a5-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="e58a5-108">Интерфейс с параметром ковариантного типа позволяет своим методам возвращать аргументы производных типов, степень наследования у которых больше, чем у параметра типа.</span><span class="sxs-lookup"><span data-stu-id="e58a5-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="e58a5-109">Например, так как в .NET Framework 4 в <xref:System.Collections.Generic.IEnumerable%601> тип T является ковариантным, можно назначить объект типа `IEnumerabe(Of String)` объекту типа `IEnumerable(Of Object)` без применения каких-либо специальных методов преобразования.</span><span class="sxs-lookup"><span data-stu-id="e58a5-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="e58a5-110">Ковариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа большей степени.</span><span class="sxs-lookup"><span data-stu-id="e58a5-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
 <span data-ttu-id="e58a5-111">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="e58a5-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e58a5-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e58a5-112">Example</span></span>  
 <span data-ttu-id="e58a5-113">В следующем примере показано, как объявить, расширить и реализовать ковариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e58a5-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="e58a5-114">В нем также показано, как использовать неявное преобразование для классов, реализующих ковариантный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e58a5-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 <span data-ttu-id="e58a5-115">[!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e58a5-115">[!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]</span></span>  
  
 <span data-ttu-id="e58a5-116">В универсальном интерфейсе параметр типа может быть объявлен ковариантным, если он удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="e58a5-116">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="e58a5-117">Параметр типа используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="e58a5-117">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e58a5-118">Существует одно исключение из данного правила.</span><span class="sxs-lookup"><span data-stu-id="e58a5-118">There is one exception to this rule.</span></span> <span data-ttu-id="e58a5-119">Если в ковариантном интерфейсе в качестве параметра метода используется контравариантный универсальный делегат, ковариантный тип можно использовать в качестве параметра универсального типа для этого делегата.</span><span class="sxs-lookup"><span data-stu-id="e58a5-119">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="e58a5-120">Дополнительные сведения о ковариантных и контравариантных универсальных методах-делегатах см. в разделе [Вариативность в делегатах](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) и [Использование вариативности в универсальных методах-делегатах Func и Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span><span class="sxs-lookup"><span data-stu-id="e58a5-120">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) and [Using Variance for Func and Action Generic Delegates](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span></span>  
  
-   <span data-ttu-id="e58a5-121">Параметр типа не используется в качестве универсального ограничения для методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e58a5-121">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e58a5-122">Пример</span><span class="sxs-lookup"><span data-stu-id="e58a5-122">Example</span></span>  
 <span data-ttu-id="e58a5-123">В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="e58a5-123">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="e58a5-124">В нем также показано, как выполнить неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="e58a5-124">It also shows how to implicitly convert delegate types.</span></span>  
  
 <span data-ttu-id="e58a5-125">[!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e58a5-125">[!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]</span></span>  
  
 <span data-ttu-id="e58a5-126">В универсальном методе-делегате тип может быть объявлен ковариантным, если он используется только как тип значения, возвращаемого методом, и не используется для аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="e58a5-126">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e58a5-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e58a5-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e58a5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e58a5-128">See Also</span></span>  
 <span data-ttu-id="e58a5-129">[Вариативность в универсальных интерфейсах](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="e58a5-129">[Variance in Generic Interfaces](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
 <span data-ttu-id="e58a5-130">[in](../../../csharp/language-reference/keywords/in-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="e58a5-130">[in](../../../csharp/language-reference/keywords/in-generic-modifier.md) </span></span>  
 [<span data-ttu-id="e58a5-131">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="e58a5-131">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

