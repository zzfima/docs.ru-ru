---
title: Оператор не может завершить блок за пределами &#39;Если&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 78fe136acbd09e202b1daeb16dd540cf42ada390
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574720"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="3f07a-102">Оператор не может завершить блок за пределами &#39;Если&#39; инструкции</span><span class="sxs-lookup"><span data-stu-id="3f07a-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="3f07a-103">Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`.</span><span class="sxs-lookup"><span data-stu-id="3f07a-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="3f07a-104">Однострочный `If` инструкций не используйте `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3f07a-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="3f07a-105">**Идентификатор ошибки:** BC32005</span><span class="sxs-lookup"><span data-stu-id="3f07a-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f07a-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3f07a-106">To correct this error</span></span>  
  
-   <span data-ttu-id="3f07a-107">Переместите однострочный `If` оператор вне блока управления, содержащего `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="3f07a-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f07a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3f07a-108">See also</span></span>
- [<span data-ttu-id="3f07a-109">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="3f07a-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
