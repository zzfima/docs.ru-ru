---
title: '&#39;Класс&#39; оператор должен заканчиваться соответствующим &#39;End Class&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 4e80ce58048bfa7f2fecc65e7167479df07bf57c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715092"
---
# <a name="39class39-statement-must-end-with-a-matching-39end-class39"></a><span data-ttu-id="5f848-102">&#39;Класс&#39; оператор должен заканчиваться соответствующим &#39;End Class&#39;</span><span class="sxs-lookup"><span data-stu-id="5f848-102">&#39;Class&#39; statement must end with a matching &#39;End Class&#39;</span></span>
<span data-ttu-id="5f848-103">`Class` используется для запуска `Class` block; поэтому он может присутствовать только в начале блока, соответствующий `End Class` инструкции, завершать этот блок.</span><span class="sxs-lookup"><span data-stu-id="5f848-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="5f848-104">Либо имеется лишний оператор `Class` инструкции, или не заканчивается на `Class` блоке с `End Class`.</span><span class="sxs-lookup"><span data-stu-id="5f848-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="5f848-105">**Идентификатор ошибки:** BC30481</span><span class="sxs-lookup"><span data-stu-id="5f848-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f848-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5f848-106">To correct this error</span></span>  
  
-   <span data-ttu-id="5f848-107">Найдите и удалите ненужный оператор `Class` .</span><span class="sxs-lookup"><span data-stu-id="5f848-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
-   <span data-ttu-id="5f848-108">В заключение `Class` блок с соответствующим `End Class`.</span><span class="sxs-lookup"><span data-stu-id="5f848-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f848-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5f848-109">See also</span></span>
- [<span data-ttu-id="5f848-110">Конец \<ключевое слово > инструкции</span><span class="sxs-lookup"><span data-stu-id="5f848-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [<span data-ttu-id="5f848-111">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="5f848-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
