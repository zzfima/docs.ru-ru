---
title: "in (универсальный модификатор) (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2af4e27034af0067e81a52c81991edaf5a5415d8
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="318ac-102">in (универсальный модификатор) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="318ac-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="318ac-103">Для параметров универсального типа ключевое слово `in` указывает, что параметр типа является контравариантным.</span><span class="sxs-lookup"><span data-stu-id="318ac-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="318ac-104">Ключевое слово `in` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="318ac-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="318ac-105">Контравариантность позволяет использовать производные типы со степенью наследования меньше, чем у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="318ac-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="318ac-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="318ac-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="318ac-107">Ковариантность и контравариантность поддерживаются для ссылочных типов, но не для типов значений.</span><span class="sxs-lookup"><span data-stu-id="318ac-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="318ac-108">Тип может быть объявлен контравариантным в универсальном интерфейсе или делегате, только если он определяет тип параметров метода, но не тип значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="318ac-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="318ac-109">Параметры `In`, `ref` и `out` должны быть инвариантными, то есть не являться ковариантными или контравариантными.</span><span class="sxs-lookup"><span data-stu-id="318ac-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>
  
 <span data-ttu-id="318ac-110">Интерфейс с параметром контравариантного типа позволяет своим методам принимать аргументы производных типов, степень наследования у которых меньше, чем у параметра типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="318ac-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="318ac-111">Например, в интерфейсе <xref:System.Collections.Generic.IComparer%601> тип T является ковариантным, поэтому можно присвоить объект типа `IComparer<Person>` объекту типа `IComparer<Employee>` без применения каких-либо специальных методов преобразования, если `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="318ac-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="318ac-112">Контравариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа меньшей степени.</span><span class="sxs-lookup"><span data-stu-id="318ac-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="318ac-113">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="318ac-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="contravariant-generic-interface"></a><span data-ttu-id="318ac-114">Контравариантный универсальный интерфейс</span><span class="sxs-lookup"><span data-stu-id="318ac-114">Contravariant generic interface</span></span>   

 <span data-ttu-id="318ac-115">В следующем примере показано, как объявить, расширить и реализовать контравариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="318ac-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="318ac-116">В нем также показано, как можно использовать неявное преобразование для классов, реализующих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="318ac-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="contravariant-generic-delegate"></a><span data-ttu-id="318ac-117">Контравариантный универсальный делегат</span><span class="sxs-lookup"><span data-stu-id="318ac-117">Contravariant generic delegate</span></span>  

 <span data-ttu-id="318ac-118">В следующем примере кода показано, как объявить контравариантный универсальный делегат.</span><span class="sxs-lookup"><span data-stu-id="318ac-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="318ac-119">В нем также показано, как можно выполнить неявное преобразование типа делегата.</span><span class="sxs-lookup"><span data-stu-id="318ac-119">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="318ac-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="318ac-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="318ac-121">См. также</span><span class="sxs-lookup"><span data-stu-id="318ac-121">See Also</span></span>  
 [<span data-ttu-id="318ac-122">out</span><span class="sxs-lookup"><span data-stu-id="318ac-122">out</span></span>](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [<span data-ttu-id="318ac-123">Ковариация и контрвариантность</span><span class="sxs-lookup"><span data-stu-id="318ac-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="318ac-124">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="318ac-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
