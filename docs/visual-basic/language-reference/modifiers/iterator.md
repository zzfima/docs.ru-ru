---
title: "Итератор (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 503d586c0515b4cb53f8ec5656e5fe765cc094a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="794db-102">Итератор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="794db-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="794db-103">Указывает, что функция или `Get` метод доступа является итератором.</span><span class="sxs-lookup"><span data-stu-id="794db-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="794db-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="794db-104">Remarks</span></span>  
 <span data-ttu-id="794db-105">*Итератор* выполняет настраиваемую итерацию по коллекции.</span><span class="sxs-lookup"><span data-stu-id="794db-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="794db-106">Итератор использует [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) инструкции для возврата всех элементов в коллекции по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="794db-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="794db-107">Когда `Yield` инструкция исчерпана, сохраняется текущее расположение в коде.</span><span class="sxs-lookup"><span data-stu-id="794db-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="794db-108">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="794db-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="794db-109">Итератор может быть реализована как функцию как `Get` доступа определения свойства.</span><span class="sxs-lookup"><span data-stu-id="794db-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="794db-110">`Iterator` Модификатор появляется в декларации функции итератора или `Get` метода доступа.</span><span class="sxs-lookup"><span data-stu-id="794db-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="794db-111">Итератор вызывается из клиентского кода с помощью [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="794db-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="794db-112">Тип возвращаемого значения функции итератора или `Get` метод доступа может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="794db-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="794db-113">Итератор не может содержать `ByRef` параметров.</span><span class="sxs-lookup"><span data-stu-id="794db-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="794db-114">Итератор не может использоваться в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.</span><span class="sxs-lookup"><span data-stu-id="794db-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="794db-115">Итератор может быть анонимной функции.</span><span class="sxs-lookup"><span data-stu-id="794db-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="794db-116">Дополнительные сведения см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="794db-116">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="794db-117">Дополнительные сведения об итераторах см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="794db-117">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="794db-118">Использование</span><span class="sxs-lookup"><span data-stu-id="794db-118">Usage</span></span>  
 <span data-ttu-id="794db-119">Модификатор `Iterator` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="794db-119">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="794db-120">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="794db-120">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="794db-121">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="794db-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="794db-122">Пример</span><span class="sxs-lookup"><span data-stu-id="794db-122">Example</span></span>  
 <span data-ttu-id="794db-123">Ниже приведен пример функции итератора.</span><span class="sxs-lookup"><span data-stu-id="794db-123">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="794db-124">Имеет функции итератора `Yield` инструкцию, которая находится внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла.</span><span class="sxs-lookup"><span data-stu-id="794db-124">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="794db-125">Каждая итерация [для каждого](../../../visual-basic/language-reference/statements/for-each-next-statement.md) тела оператора в `Main` создает вызов `Power` функции итератора.</span><span class="sxs-lookup"><span data-stu-id="794db-125">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="794db-126">При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="794db-126">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="794db-127">Пример</span><span class="sxs-lookup"><span data-stu-id="794db-127">Example</span></span>  
 <span data-ttu-id="794db-128">В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор.</span><span class="sxs-lookup"><span data-stu-id="794db-128">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="794db-129">`Iterator` Имеет модификатор в объявлении свойства.</span><span class="sxs-lookup"><span data-stu-id="794db-129">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 <span data-ttu-id="794db-130">Дополнительные примеры см. в разделе [итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="794db-130">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794db-131">См. также</span><span class="sxs-lookup"><span data-stu-id="794db-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [<span data-ttu-id="794db-132">Итераторы</span><span class="sxs-lookup"><span data-stu-id="794db-132">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="794db-133">Оператор Yield</span><span class="sxs-lookup"><span data-stu-id="794db-133">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
