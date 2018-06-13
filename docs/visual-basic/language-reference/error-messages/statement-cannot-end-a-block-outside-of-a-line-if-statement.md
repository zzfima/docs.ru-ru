---
title: Оператор не может завершить блок за пределами &#39;Если&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596688"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="56ede-102">Оператор не может завершить блок за пределами &#39;Если&#39; инструкции</span><span class="sxs-lookup"><span data-stu-id="56ede-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="56ede-103">Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`.</span><span class="sxs-lookup"><span data-stu-id="56ede-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="56ede-104">Однострочный `If` не используйте инструкции `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="56ede-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="56ede-105">**Идентификатор ошибки:** BC32005</span><span class="sxs-lookup"><span data-stu-id="56ede-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="56ede-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="56ede-106">To correct this error</span></span>  
  
-   <span data-ttu-id="56ede-107">Переместите однострочный `If` инструкции вне блока управления, содержащий `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="56ede-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ede-108">См. также</span><span class="sxs-lookup"><span data-stu-id="56ede-108">See Also</span></span>  
 [<span data-ttu-id="56ede-109">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="56ede-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
