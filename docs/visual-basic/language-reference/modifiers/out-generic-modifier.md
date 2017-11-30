---
title: "Out (универсальный модификатор) (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94d18200e6d7ce0ad63a229223ae77d99302e0e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="36702-102">Out (универсальный модификатор) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36702-102">Out (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="36702-103">Для параметров универсального типа `Out` ключевое слово указывает, что тип является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="36702-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36702-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="36702-104">Remarks</span></span>  
 <span data-ttu-id="36702-105">Ковариация позволяет использовать производные типы со степенью наследования больше, нежели у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="36702-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="36702-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="36702-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="36702-107">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="36702-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="36702-108">Правила</span><span class="sxs-lookup"><span data-stu-id="36702-108">Rules</span></span>  
 <span data-ttu-id="36702-109">Ключевое слово `Out` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="36702-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="36702-110">В универсальном интерфейсе параметр типа может быть объявлен ковариантным, если он удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="36702-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>  
  
-   <span data-ttu-id="36702-111">Параметр типа используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="36702-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="36702-112">Существует одно исключение из данного правила.</span><span class="sxs-lookup"><span data-stu-id="36702-112">There is one exception to this rule.</span></span> <span data-ttu-id="36702-113">Если в ковариантном интерфейсе в качестве параметра метода используется контравариантный универсальный делегат, ковариантный тип можно использовать в качестве параметра универсального типа для этого делегата.</span><span class="sxs-lookup"><span data-stu-id="36702-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="36702-114">Дополнительные сведения о ковариантных и контравариантных универсальных методах-делегатах см. в разделе [Вариативность в делегатах](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) и [Использование вариативности в универсальных методах-делегатах Func и Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span><span class="sxs-lookup"><span data-stu-id="36702-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) and [Using Variance for Func and Action Generic Delegates](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).</span></span>  
  
-   <span data-ttu-id="36702-115">Параметр типа не используется в качестве универсального ограничения для методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="36702-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>  
  
 <span data-ttu-id="36702-116">В универсального делегата параметр типа может быть объявлен ковариантным, если он используется только в качестве типа возвращаемого значения метода и не используется для аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="36702-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>  
  
 <span data-ttu-id="36702-117">Ковариация и контравариантность поддерживаются для ссылочных типов, но не для типов значений.</span><span class="sxs-lookup"><span data-stu-id="36702-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="36702-118">В Visual Basic нельзя объявлять события в ковариантных интерфейсах без указания типа делегата.</span><span class="sxs-lookup"><span data-stu-id="36702-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="36702-119">Кроме того ковариантный интерфейс не может включать вложенные классы, перечисления или структуры, но может включать вложенные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="36702-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="36702-120">Поведение</span><span class="sxs-lookup"><span data-stu-id="36702-120">Behavior</span></span>  
 <span data-ttu-id="36702-121">Интерфейс с параметром ковариантного типа позволяет своим методам возвращать аргументы производных типов, степень наследования у которых больше, чем у параметра типа.</span><span class="sxs-lookup"><span data-stu-id="36702-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="36702-122">Например, так как в .NET Framework 4 в <xref:System.Collections.Generic.IEnumerable%601> тип T является ковариантным, можно назначить объект типа `IEnumerabe(Of String)` объекту типа `IEnumerable(Of Object)` без применения каких-либо специальных методов преобразования.</span><span class="sxs-lookup"><span data-stu-id="36702-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerabe(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>  
  
 <span data-ttu-id="36702-123">Ковариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа большей степени.</span><span class="sxs-lookup"><span data-stu-id="36702-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36702-124">Пример</span><span class="sxs-lookup"><span data-stu-id="36702-124">Example</span></span>  
 <span data-ttu-id="36702-125">В следующем примере показано, как объявить, расширить и реализовать ковариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="36702-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="36702-126">В нем также показано, как использовать неявное преобразование для классов, реализующих ковариантный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="36702-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="36702-127">Пример</span><span class="sxs-lookup"><span data-stu-id="36702-127">Example</span></span>  
 <span data-ttu-id="36702-128">В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="36702-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="36702-129">Также показано, как используется неявное преобразование для типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="36702-129">It also shows how you can use implicit conversion for delegate types.</span></span>  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="36702-130">См. также</span><span class="sxs-lookup"><span data-stu-id="36702-130">See Also</span></span>  
 [<span data-ttu-id="36702-131">Расхождение в универсальных интерфейсах</span><span class="sxs-lookup"><span data-stu-id="36702-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="36702-132">In</span><span class="sxs-lookup"><span data-stu-id="36702-132">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
