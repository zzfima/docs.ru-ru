---
title: "out (универсальный модификатор) (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 25019408387bbf085475482c74a3fc6001321b24
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="5129d-102">out (универсальный модификатор) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5129d-102">out (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="5129d-103">Для параметров универсального типа ключевое слово `out` указывает, что параметр типа является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="5129d-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="5129d-104">Ключевое слово `out` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="5129d-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="5129d-105">Ковариация позволяет использовать производные типы со степенью наследования больше, нежели у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="5129d-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="5129d-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="5129d-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="5129d-107">Ковариация и контравариантность поддерживаются для ссылочных типов, но не для типов значений.</span><span class="sxs-lookup"><span data-stu-id="5129d-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="5129d-108">Интерфейс с параметром ковариантного типа позволяет своим методам возвращать аргументы производных типов, степень наследования у которых больше, чем у параметра типа.</span><span class="sxs-lookup"><span data-stu-id="5129d-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="5129d-109">Например, так как в .NET Framework 4 в <xref:System.Collections.Generic.IEnumerable%601> тип T является ковариантным, можно назначить объект типа `IEnumerable(Of String)` объекту типа `IEnumerable(Of Object)` без применения каких-либо специальных методов преобразования.</span><span class="sxs-lookup"><span data-stu-id="5129d-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="5129d-110">Ковариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа большей степени.</span><span class="sxs-lookup"><span data-stu-id="5129d-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
 <span data-ttu-id="5129d-111">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="5129d-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5129d-112">Пример</span><span class="sxs-lookup"><span data-stu-id="5129d-112">Example</span></span>  
 <span data-ttu-id="5129d-113">В следующем примере показано, как объявить, расширить и реализовать ковариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5129d-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="5129d-114">В нем также показано, как использовать неявное преобразование для классов, реализующих ковариантный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5129d-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 [!code-csharp[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]  
  
 <span data-ttu-id="5129d-115">В универсальном интерфейсе параметр типа может быть объявлен ковариантным, если он удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="5129d-115">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="5129d-116">Параметр типа используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="5129d-116">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5129d-117">Существует одно исключение из данного правила.</span><span class="sxs-lookup"><span data-stu-id="5129d-117">There is one exception to this rule.</span></span> <span data-ttu-id="5129d-118">Если в ковариантном интерфейсе в качестве параметра метода используется контравариантный универсальный делегат, ковариантный тип можно использовать в качестве параметра универсального типа для этого делегата.</span><span class="sxs-lookup"><span data-stu-id="5129d-118">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="5129d-119">Дополнительные сведения о ковариантных и контравариантных универсальных методах-делегатах см. в разделе [Вариативность в делегатах](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [Использование вариативности в универсальных методах-делегатах Func и Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5129d-119">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
-   <span data-ttu-id="5129d-120">Параметр типа не используется в качестве универсального ограничения для методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5129d-120">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5129d-121">Пример</span><span class="sxs-lookup"><span data-stu-id="5129d-121">Example</span></span>  
 <span data-ttu-id="5129d-122">В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="5129d-122">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="5129d-123">В нем также показано, как выполнить неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="5129d-123">It also shows how to implicitly convert delegate types.</span></span>  
  
 [!code-csharp[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]  
  
 <span data-ttu-id="5129d-124">В универсальном методе-делегате тип может быть объявлен ковариантным, если он используется только как тип значения, возвращаемого методом, и не используется для аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="5129d-124">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5129d-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5129d-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5129d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5129d-126">See Also</span></span>  
 [<span data-ttu-id="5129d-127">Расхождение в универсальных интерфейсах</span><span class="sxs-lookup"><span data-stu-id="5129d-127">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="5129d-128">in</span><span class="sxs-lookup"><span data-stu-id="5129d-128">in</span></span>](../../../csharp/language-reference/keywords/in-generic-modifier.md)  
 [<span data-ttu-id="5129d-129">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="5129d-129">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
