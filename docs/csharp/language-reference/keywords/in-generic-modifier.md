---
title: Справочник по C#. Универсальный модификатор in
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: 0806169b9b1c3521dcf89f5ea0fa5aec188030c2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422773"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="7b3d9-102">in (универсальный модификатор) (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7b3d9-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="7b3d9-103">Для параметров универсального типа ключевое слово `in` указывает, что параметр типа является контравариантным.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="7b3d9-104">Ключевое слово `in` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="7b3d9-105">Контравариантность позволяет использовать производные типы со степенью наследования меньше, чем у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="7b3d9-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих контравариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-106">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="7b3d9-107">Ковариантность и контравариантность поддерживаются для ссылочных типов, но не для типов значений.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="7b3d9-108">Тип может быть объявлен контравариантным в универсальном интерфейсе или делегате, только если он определяет тип параметров метода, но не тип значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="7b3d9-109">Параметры `In`, `ref` и `out` должны быть инвариантными, то есть не являться ковариантными или контравариантными.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="7b3d9-110">Интерфейс с параметром контравариантного типа позволяет своим методам принимать аргументы производных типов, степень наследования у которых меньше, чем у параметра типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="7b3d9-111">Например, в интерфейсе <xref:System.Collections.Generic.IComparer%601> тип T является контравариантным, поэтому можно присвоить объект типа `IComparer<Person>` объекту типа `IComparer<Employee>` без применения каких-либо специальных методов преобразования, если `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="7b3d9-112">Контравариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа меньшей степени.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="7b3d9-113">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="7b3d9-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="7b3d9-114">Контравариантный универсальный интерфейс</span><span class="sxs-lookup"><span data-stu-id="7b3d9-114">Contravariant generic interface</span></span>

<span data-ttu-id="7b3d9-115">В следующем примере показано, как объявить, расширить и реализовать контравариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="7b3d9-116">В нем также показано, как можно использовать неявное преобразование для классов, реализующих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="7b3d9-117">Контравариантный универсальный делегат</span><span class="sxs-lookup"><span data-stu-id="7b3d9-117">Contravariant generic delegate</span></span>

<span data-ttu-id="7b3d9-118">В следующем примере кода показано, как объявить контравариантный универсальный делегат.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="7b3d9-119">В нем также показано, как можно выполнить неявное преобразование типа делегата.</span><span class="sxs-lookup"><span data-stu-id="7b3d9-119">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="7b3d9-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7b3d9-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7b3d9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7b3d9-121">See also</span></span>

- [<span data-ttu-id="7b3d9-122">out</span><span class="sxs-lookup"><span data-stu-id="7b3d9-122">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="7b3d9-123">Ковариация и контрвариантность</span><span class="sxs-lookup"><span data-stu-id="7b3d9-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="7b3d9-124">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="7b3d9-124">Modifiers</span></span>](index.md)
