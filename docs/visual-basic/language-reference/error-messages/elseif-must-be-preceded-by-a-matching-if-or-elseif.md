---
title: 'Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: fbb8ce974a618349bd4b5e7a2a25a165d91787a7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832259"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="308b7-102">Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf</span><span class="sxs-lookup"><span data-stu-id="308b7-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="308b7-103">`#ElseIf` является директивой условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="308b7-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="308b7-104">`#ElseIf` Предложение должен предшествовать соответствующий `#If` или `#ElseIf` предложение.</span><span class="sxs-lookup"><span data-stu-id="308b7-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="308b7-105">**Идентификатор ошибки:** BC30014</span><span class="sxs-lookup"><span data-stu-id="308b7-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="308b7-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="308b7-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="308b7-107">Убедитесь, что предшествующий `#If` или `#ElseIf` не отделена от этого `#ElseIf` блоком условной компиляции или неправильно размещенной директивой `#End If`.</span><span class="sxs-lookup"><span data-stu-id="308b7-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="308b7-108">Если `#ElseIf` предшествует `#Else` директива, либо удалите `#Else` или измените его на `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="308b7-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="308b7-109">Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="308b7-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="308b7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="308b7-110">See also</span></span>

- [<span data-ttu-id="308b7-111">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="308b7-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
