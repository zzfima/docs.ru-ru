---
title: Оператор не может завершить блок за пределами однострочной инструкции If
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825798"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="64a56-102">Оператор не может завершить блок за пределами однострочной инструкции If</span><span class="sxs-lookup"><span data-stu-id="64a56-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="64a56-103">Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`.</span><span class="sxs-lookup"><span data-stu-id="64a56-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="64a56-104">Однострочный `If` инструкций не используйте `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="64a56-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="64a56-105">**Идентификатор ошибки:** BC32005</span><span class="sxs-lookup"><span data-stu-id="64a56-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="64a56-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="64a56-106">To correct this error</span></span>  
  
-   <span data-ttu-id="64a56-107">Переместите однострочный `If` оператор вне блока управления, содержащего `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="64a56-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a56-108">См. также</span><span class="sxs-lookup"><span data-stu-id="64a56-108">See also</span></span>

- [<span data-ttu-id="64a56-109">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="64a56-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
