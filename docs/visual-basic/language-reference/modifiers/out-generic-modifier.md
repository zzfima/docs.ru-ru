---
title: out (универсальный модификатор)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: 0460015b44971fa638dba47183690ffcc89ca55f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351427"
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="4cfb7-102">Out (универсальный модификатор) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cfb7-102">Out (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="4cfb7-103">Для параметров универсального типа ключевое слово `Out` указывает, что тип является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cfb7-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="4cfb7-104">Remarks</span></span>

<span data-ttu-id="4cfb7-105">Ковариация позволяет использовать производные типы со степенью наследования больше, нежели у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="4cfb7-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="4cfb7-107">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="4cfb7-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="4cfb7-108">Правила</span><span class="sxs-lookup"><span data-stu-id="4cfb7-108">Rules</span></span>

<span data-ttu-id="4cfb7-109">Ключевое слово `Out` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="4cfb7-110">В универсальном интерфейсе параметр типа может быть объявлен ковариантным, если он удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="4cfb7-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="4cfb7-111">Параметр типа используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4cfb7-112">Существует одно исключение из данного правила.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-112">There is one exception to this rule.</span></span> <span data-ttu-id="4cfb7-113">Если в ковариантном интерфейсе в качестве параметра метода используется контравариантный универсальный делегат, ковариантный тип можно использовать в качестве параметра универсального типа для этого делегата.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="4cfb7-114">Дополнительные сведения о ковариантных и контравариантных универсальных методах-делегатах см. в разделе [Вариативность в делегатах](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [Использование вариативности в универсальных методах-делегатах Func и Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="4cfb7-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="4cfb7-115">Параметр типа не используется в качестве универсального ограничения для методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>

<span data-ttu-id="4cfb7-116">В универсальном делегате параметр типа может быть объявлен ковариантным, если он используется только в качестве возвращаемого типа метода и не используется для аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

<span data-ttu-id="4cfb7-117">Ковариация и контравариантность поддерживаются для ссылочных типов, но не для типов значений.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="4cfb7-118">В Visual Basic нельзя объявлять события в ковариантных интерфейсах без указания типа делегата.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="4cfb7-119">Кроме того, ковариантные интерфейсы не могут иметь вложенные классы, перечисления или структуры, но они могут иметь вложенные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="4cfb7-120">Поведение</span><span class="sxs-lookup"><span data-stu-id="4cfb7-120">Behavior</span></span>

<span data-ttu-id="4cfb7-121">Интерфейс с параметром ковариантного типа позволяет своим методам возвращать аргументы производных типов, степень наследования у которых больше, чем у параметра типа.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="4cfb7-122">Например, так как в .NET Framework 4 в <xref:System.Collections.Generic.IEnumerable%601> тип T является ковариантным, можно назначить объект типа `IEnumerable(Of String)` объекту типа `IEnumerable(Of Object)` без применения каких-либо специальных методов преобразования.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="4cfb7-123">Ковариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа большей степени.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="4cfb7-124">Пример</span><span class="sxs-lookup"><span data-stu-id="4cfb7-124">Example</span></span>

<span data-ttu-id="4cfb7-125">В следующем примере показано, как объявить, расширить и реализовать ковариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="4cfb7-126">В нем также показано, как использовать неявное преобразование для классов, реализующих ковариантный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="4cfb7-127">Пример</span><span class="sxs-lookup"><span data-stu-id="4cfb7-127">Example</span></span>

<span data-ttu-id="4cfb7-128">В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="4cfb7-129">Здесь также показано, как можно использовать неявное преобразование для типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="4cfb7-129">It also shows how you can use implicit conversion for delegate types.</span></span>

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="4cfb7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4cfb7-130">See also</span></span>

- [<span data-ttu-id="4cfb7-131">Расхождение в универсальных интерфейсах</span><span class="sxs-lookup"><span data-stu-id="4cfb7-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="4cfb7-132">In</span><span class="sxs-lookup"><span data-stu-id="4cfb7-132">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
