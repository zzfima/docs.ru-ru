---
title: In (универсальный модификатор) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: d8d503f0814a89c977cdc208eced026b2d8cb1fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802477"
---
# <a name="in-generic-modifier-visual-basic"></a><span data-ttu-id="16612-102">In (универсальный модификатор) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16612-102">In (Generic Modifier) (Visual Basic)</span></span>
<span data-ttu-id="16612-103">Для параметров универсального типа ключевое слово `In` указывает, что параметр типа является контравариантным.</span><span class="sxs-lookup"><span data-stu-id="16612-103">For generic type parameters, the `In` keyword specifies that the type parameter is contravariant.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16612-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="16612-104">Remarks</span></span>  
 <span data-ttu-id="16612-105">Контравариантность позволяет использовать производные типы со степенью наследования меньше, чем у типа, заданного универсальным параметром.</span><span class="sxs-lookup"><span data-stu-id="16612-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="16612-106">Благодаря этому можно осуществлять неявное преобразование классов, реализующих вариантные интерфейсы, и неявное преобразование типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="16612-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>  
  
 <span data-ttu-id="16612-107">Дополнительные сведения см. в разделе [Ковариация и контравариантность](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="16612-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="16612-108">Правила</span><span class="sxs-lookup"><span data-stu-id="16612-108">Rules</span></span>  
 <span data-ttu-id="16612-109">Ключевое слово `In` может применяться в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="16612-109">You can use the `In` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="16612-110">Параметр типа может быть объявлен контравариантным в универсальном интерфейсе или делегате, если он используется только в качестве типа аргументов метода и не используется в качестве типа возвращаемого значения метода.</span><span class="sxs-lookup"><span data-stu-id="16612-110">A type parameter can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="16612-111">`ByRef` параметры не могут быть ковариантными или контравариантными.</span><span class="sxs-lookup"><span data-stu-id="16612-111">`ByRef` parameters cannot be covariant or contravariant.</span></span>  
  
 <span data-ttu-id="16612-112">Ковариация и контравариантность поддерживаются для ссылочных типов и не поддерживается для типов значений.</span><span class="sxs-lookup"><span data-stu-id="16612-112">Covariance and contravariance are supported for reference types and not supported for value types.</span></span>  
  
 <span data-ttu-id="16612-113">В Visual Basic нельзя объявлять события в интерфейсах контравариантным без указания типа делегата.</span><span class="sxs-lookup"><span data-stu-id="16612-113">In Visual Basic, you cannot declare events in contravariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="16612-114">Кроме того контравариантный интерфейс не может включать вложенные классы, перечисления или структуры, но они могут иметь вложенные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="16612-114">Also, contravariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="16612-115">Поведение</span><span class="sxs-lookup"><span data-stu-id="16612-115">Behavior</span></span>  
 <span data-ttu-id="16612-116">Интерфейс с параметром контравариантного типа позволяет своим методам принимать аргументы производных типов, степень наследования у которых меньше, чем у параметра типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="16612-116">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="16612-117">Например, поскольку в .NET Framework 4 в интерфейсе <xref:System.Collections.Generic.IComparer%601> тип T является ковариантным, можно присвоить объект типа `IComparer(Of Person)` объекту типа `IComparer(Of Employee)` без применения каких-либо специальных методов преобразования, если `Person` наследует `Employee`.</span><span class="sxs-lookup"><span data-stu-id="16612-117">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Person` inherits `Employee`.</span></span>  
  
 <span data-ttu-id="16612-118">Контравариантный делегат может быть назначен другому делегату того же типа, но с производным параметром универсального типа меньшей степени.</span><span class="sxs-lookup"><span data-stu-id="16612-118">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16612-119">Пример</span><span class="sxs-lookup"><span data-stu-id="16612-119">Example</span></span>  
 <span data-ttu-id="16612-120">В следующем примере показано, как объявить, расширить и реализовать контравариантный универсальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="16612-120">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="16612-121">В нем также показано, как можно использовать неявное преобразование для классов, реализующих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="16612-121">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="16612-122">Пример</span><span class="sxs-lookup"><span data-stu-id="16612-122">Example</span></span>  
 <span data-ttu-id="16612-123">В следующем примере кода показано, как объявить контравариантный универсальный делегат.</span><span class="sxs-lookup"><span data-stu-id="16612-123">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="16612-124">В нем также показано, как можно выполнить неявное преобразование типа делегата.</span><span class="sxs-lookup"><span data-stu-id="16612-124">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="16612-125">См. также</span><span class="sxs-lookup"><span data-stu-id="16612-125">See also</span></span>

- [<span data-ttu-id="16612-126">Расхождение в универсальных интерфейсах</span><span class="sxs-lookup"><span data-stu-id="16612-126">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="16612-127">Out</span><span class="sxs-lookup"><span data-stu-id="16612-127">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
