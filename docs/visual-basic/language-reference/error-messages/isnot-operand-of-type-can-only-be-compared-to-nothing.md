---
title: '&#39;IsNot&#39; операнд типа &#39;typename&#39; может сравниваться только с &#39;ничего не&#39;, так как &#39;typename&#39; допускает значение NULL'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 65b04c85bccd169bbb2eea847d7b8af96c1a292f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505722"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="1f502-102">&#39;IsNot&#39; операнд типа &#39;typename&#39; может сравниваться только с &#39;ничего не&#39;, так как &#39;typename&#39; допускает значение NULL</span><span class="sxs-lookup"><span data-stu-id="1f502-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="1f502-103">Переменная, объявленная как допускающая значение NULL, сравнивалась с выражением отличное от `Nothing` с помощью `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="1f502-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="1f502-104">**Идентификатор ошибки:** BC32128</span><span class="sxs-lookup"><span data-stu-id="1f502-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f502-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1f502-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="1f502-106">Чтобы сравнить тип, допускающий значение null, с выражением, отличным от `Nothing` , с помощью оператора `IsNot` , вызовите метод `GetType` для типа, допускающего значение null, и сравните результат с выражением, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1f502-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f502-107">См. также</span><span class="sxs-lookup"><span data-stu-id="1f502-107">See also</span></span>
- [<span data-ttu-id="1f502-108">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="1f502-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="1f502-109">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="1f502-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
