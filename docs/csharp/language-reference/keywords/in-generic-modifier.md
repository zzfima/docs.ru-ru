---
title: "in (универсальный модификатор) (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
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
ms.openlocfilehash: 663fa75a7e214ed97efb45dda2c9ac298559653d
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="6ef3d-102">in (универсальный модификатор) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6ef3d-102">in (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="6ef3d-103">Для параметров универсального типа ключевое слово `in` указывает, что параметр типа является контравариантным.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="6ef3d-104">Ключевое слово `in` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="6ef3d-105">Контравариантность позволяет использовать производные типы со степенью наследования меньше, чем у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="6ef3d-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="6ef3d-107">Ковариантность и контравариантность поддерживаются для ссылочных типов, но не для типов значений.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="6ef3d-108">Тип может быть объявлен контравариантным в универсальном интерфейсе или делегате, если он используется только как тип аргументов метода, но не как тип значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-108">A type can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="6ef3d-109">Параметры `Ref` и `out` не могут быть вариантными.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-109">`Ref` and `out` parameters cannot be variant.</span></span>  
  
 <span data-ttu-id="6ef3d-110">Интерфейс с параметром контравариантного типа позволяет своим методам принимать аргументы производных типов, степень наследования у которых меньше, чем у параметра типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="6ef3d-111">Например, поскольку в .NET Framework 4 в интерфейсе <xref:System.Collections.Generic.IComparer%601> тип T является ковариантным, можно присвоить объект типа `IComparer(Of Person)` объекту типа `IComparer(Of Employee)` без применения каких-либо специальных методов преобразования, если `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-111">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="6ef3d-112">Контравариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа меньшей степени.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="6ef3d-113">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="6ef3d-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ef3d-114">Пример</span><span class="sxs-lookup"><span data-stu-id="6ef3d-114">Example</span></span>  
 <span data-ttu-id="6ef3d-115">В следующем примере показано, как объявить, расширить и реализовать контравариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="6ef3d-116">В нем также показано, как можно использовать неявное преобразование для классов, реализующих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 <span data-ttu-id="6ef3d-117">[!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6ef3d-117">[!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ef3d-118">Пример</span><span class="sxs-lookup"><span data-stu-id="6ef3d-118">Example</span></span>  
 <span data-ttu-id="6ef3d-119">В следующем примере кода показано, как объявить контравариантный универсальный делегат.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-119">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="6ef3d-120">В нем также показано, как можно выполнить неявное преобразование типа делегата.</span><span class="sxs-lookup"><span data-stu-id="6ef3d-120">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 <span data-ttu-id="6ef3d-121">[!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6ef3d-121">[!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6ef3d-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6ef3d-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ef3d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6ef3d-123">See Also</span></span>  
 <span data-ttu-id="6ef3d-124">[out](../../../csharp/language-reference/keywords/out-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="6ef3d-124">[out](../../../csharp/language-reference/keywords/out-generic-modifier.md) </span></span>  
 <span data-ttu-id="6ef3d-125">[Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ef3d-125">[Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md) </span></span>  
 [<span data-ttu-id="6ef3d-126">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="6ef3d-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

