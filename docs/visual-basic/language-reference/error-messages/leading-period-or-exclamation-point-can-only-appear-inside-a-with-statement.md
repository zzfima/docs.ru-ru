---
title: Начальные &#39;. &#39; или &#39;! &#39; может располагаться только внутри &#39;с&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625956"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="17c95-102">Начальные &#39;. &#39; или &#39;! &#39; может располагаться только внутри &#39;с&#39; инструкции</span><span class="sxs-lookup"><span data-stu-id="17c95-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="17c95-103">Точка (.) или восклицательный знак (!), не находится внутри `With` блок происходит без выражения в левой части.</span><span class="sxs-lookup"><span data-stu-id="17c95-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="17c95-104">Доступ к членам (`.`) и доступ к членам словаря (`!`) требуется выражение, задающее элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="17c95-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="17c95-105">Это должно быть расположено слева метода доступа или в качестве целевого объекта `With` блока, содержащего доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="17c95-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="17c95-106">**Идентификатор ошибки:** BC30157</span><span class="sxs-lookup"><span data-stu-id="17c95-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="17c95-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="17c95-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="17c95-108">Убедитесь, что `With` блок имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="17c95-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="17c95-109">Если нет `With` block, добавьте выражение слева от метода доступа, результатом вычисления элемента, содержащего элемент.</span><span class="sxs-lookup"><span data-stu-id="17c95-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c95-110">См. также</span><span class="sxs-lookup"><span data-stu-id="17c95-110">See also</span></span>
- [<span data-ttu-id="17c95-111">Специальные символы в коде</span><span class="sxs-lookup"><span data-stu-id="17c95-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="17c95-112">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="17c95-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
