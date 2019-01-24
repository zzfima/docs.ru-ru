---
title: '&#39;#ElseIf&#39; должен предшествовать соответствующий &#39;#If&#39; или &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 1e63595ee573e9356f6870a02b2131897c725baf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505787"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="b3127-102">&#39;#ElseIf&#39; должен предшествовать соответствующий &#39;#If&#39; или &#39;#ElseIf&#39;</span><span class="sxs-lookup"><span data-stu-id="b3127-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="b3127-103">`#ElseIf` является директивой условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="b3127-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="b3127-104">`#ElseIf` Предложение должен предшествовать соответствующий `#If` или `#ElseIf` предложение.</span><span class="sxs-lookup"><span data-stu-id="b3127-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="b3127-105">**Идентификатор ошибки:** BC30014</span><span class="sxs-lookup"><span data-stu-id="b3127-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b3127-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b3127-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b3127-107">Убедитесь, что предшествующий `#If` или `#ElseIf` не отделена от этого `#ElseIf` блоком условной компиляции или неправильно размещенной директивой `#End If`.</span><span class="sxs-lookup"><span data-stu-id="b3127-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="b3127-108">Если `#ElseIf` предшествует `#Else` директива, либо удалите `#Else` или измените его на `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="b3127-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="b3127-109">Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="b3127-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3127-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b3127-110">See also</span></span>
- [<span data-ttu-id="b3127-111">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="b3127-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
