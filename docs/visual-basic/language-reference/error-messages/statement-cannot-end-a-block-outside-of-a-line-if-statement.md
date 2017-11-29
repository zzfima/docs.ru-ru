---
title: "Оператор не может завершить блок за пределами строки &#39; Если &#39; инструкции"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords: BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73fe3eb44e904366db7d505bbe8c5fef461eb78b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="9923d-102">Оператор не может завершить блок за пределами строки &#39; Если &#39; инструкции</span><span class="sxs-lookup"><span data-stu-id="9923d-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="9923d-103">Однострочный `If` инструкция содержит несколько операторов, разделенных двоеточием (:), один из которых является `End` инструкции для блока управления за пределами однострочного `If`.</span><span class="sxs-lookup"><span data-stu-id="9923d-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="9923d-104">Однострочный `If` не используйте инструкции `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="9923d-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="9923d-105">**Идентификатор ошибки:** BC32005</span><span class="sxs-lookup"><span data-stu-id="9923d-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9923d-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9923d-106">To correct this error</span></span>  
  
-   <span data-ttu-id="9923d-107">Переместите однострочный `If` инструкции вне блока управления, содержащий `End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="9923d-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9923d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9923d-108">See Also</span></span>  
 [<span data-ttu-id="9923d-109">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="9923d-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
