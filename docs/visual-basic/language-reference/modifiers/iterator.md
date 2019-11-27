---
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 9d7eaf186bae544031487ce027505e1e0d4ae0f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351526"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="e60fb-102">Итератор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e60fb-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="e60fb-103">Указывает, что функция или метод доступа `Get` являются итератором.</span><span class="sxs-lookup"><span data-stu-id="e60fb-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e60fb-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="e60fb-104">Remarks</span></span>  
 <span data-ttu-id="e60fb-105">*Итератор* выполняет настраиваемую итерацию по коллекции.</span><span class="sxs-lookup"><span data-stu-id="e60fb-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="e60fb-106">Итератор использует оператор [yield](../../../visual-basic/language-reference/statements/yield-statement.md) для возвращения каждого элемента в коллекции по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="e60fb-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="e60fb-107">При достижении оператора `Yield` текущее место в коде сохраняется.</span><span class="sxs-lookup"><span data-stu-id="e60fb-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="e60fb-108">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="e60fb-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="e60fb-109">Итератор может быть реализован как функция или как метод доступа `Get` для определения свойства.</span><span class="sxs-lookup"><span data-stu-id="e60fb-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="e60fb-110">Модификатор `Iterator` отображается в объявлении функции итератора или методе доступа `Get`.</span><span class="sxs-lookup"><span data-stu-id="e60fb-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="e60fb-111">Итератор вызывается из клиентского кода с помощью метода [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e60fb-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="e60fb-112">Тип возвращаемого значения функции итератора или метода доступа `Get` может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>или <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="e60fb-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="e60fb-113">Итератор не может иметь никаких `ByRef` параметров.</span><span class="sxs-lookup"><span data-stu-id="e60fb-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="e60fb-114">Итератор не может использоваться в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.</span><span class="sxs-lookup"><span data-stu-id="e60fb-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="e60fb-115">Итератор может быть анонимной функцией.</span><span class="sxs-lookup"><span data-stu-id="e60fb-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="e60fb-116">Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="e60fb-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="e60fb-117">Использование</span><span class="sxs-lookup"><span data-stu-id="e60fb-117">Usage</span></span>  
 <span data-ttu-id="e60fb-118">Модификатор `Iterator` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="e60fb-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
- [<span data-ttu-id="e60fb-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="e60fb-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="e60fb-120">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="e60fb-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="e60fb-121">Пример</span><span class="sxs-lookup"><span data-stu-id="e60fb-121">Example</span></span>  
 <span data-ttu-id="e60fb-122">В следующем примере демонстрируется функция итератора.</span><span class="sxs-lookup"><span data-stu-id="e60fb-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="e60fb-123">Функция итератора содержит оператор `Yield`, который находится внутри блока [for... Следующий](../../../visual-basic/language-reference/statements/for-next-statement.md) цикл.</span><span class="sxs-lookup"><span data-stu-id="e60fb-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="e60fb-124">Каждая итерация тела оператора [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) в `Main` создает вызов функции итератора `Power`.</span><span class="sxs-lookup"><span data-stu-id="e60fb-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="e60fb-125">При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="e60fb-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="e60fb-126">Пример</span><span class="sxs-lookup"><span data-stu-id="e60fb-126">Example</span></span>  
 <span data-ttu-id="e60fb-127">В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор.</span><span class="sxs-lookup"><span data-stu-id="e60fb-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="e60fb-128">Модификатор `Iterator` находится в объявлении свойства.</span><span class="sxs-lookup"><span data-stu-id="e60fb-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="e60fb-129">Дополнительные примеры см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="e60fb-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60fb-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e60fb-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="e60fb-131">Итераторы</span><span class="sxs-lookup"><span data-stu-id="e60fb-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="e60fb-132">Оператор Yield</span><span class="sxs-lookup"><span data-stu-id="e60fb-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
