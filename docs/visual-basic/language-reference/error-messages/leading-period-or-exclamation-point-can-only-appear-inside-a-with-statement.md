---
title: Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 367da8e7c9fd8c14a16a09b1f023e7637d78309d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259561"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="c2749-102">Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"</span><span class="sxs-lookup"><span data-stu-id="c2749-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="c2749-103">Точка (.) или восклицательный знак (!), не находится внутри `With` блок происходит без выражения в левой части.</span><span class="sxs-lookup"><span data-stu-id="c2749-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="c2749-104">Доступ к членам (`.`) и доступ к членам словаря (`!`) требуется выражение, задающее элемент, содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="c2749-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="c2749-105">Это должно быть расположено слева метода доступа или в качестве целевого объекта `With` блока, содержащего доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="c2749-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="c2749-106">**Идентификатор ошибки:** BC30157</span><span class="sxs-lookup"><span data-stu-id="c2749-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2749-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c2749-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="c2749-108">Убедитесь, что `With` блок имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="c2749-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="c2749-109">Если нет `With` block, добавьте выражение слева от метода доступа, результатом вычисления элемента, содержащего элемент.</span><span class="sxs-lookup"><span data-stu-id="c2749-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2749-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c2749-110">See also</span></span>
- [<span data-ttu-id="c2749-111">Специальные символы в коде</span><span class="sxs-lookup"><span data-stu-id="c2749-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="c2749-112">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="c2749-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
