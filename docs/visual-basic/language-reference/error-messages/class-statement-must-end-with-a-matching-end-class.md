---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 572e1d74810aad6d24e6eefc8d37729f5dc950c9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286953"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="404a3-102">Оператор Class должен заканчиваться соответствующим End Class</span><span class="sxs-lookup"><span data-stu-id="404a3-102">'Class' statement must end with a matching 'End Class'</span></span>
<span data-ttu-id="404a3-103">`Class` используется для запуска `Class` block; поэтому он может присутствовать только в начале блока, соответствующий `End Class` инструкции, завершать этот блок.</span><span class="sxs-lookup"><span data-stu-id="404a3-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="404a3-104">Либо имеется лишний оператор `Class` инструкции, или не заканчивается на `Class` блоке с `End Class`.</span><span class="sxs-lookup"><span data-stu-id="404a3-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="404a3-105">**Идентификатор ошибки:** BC30481</span><span class="sxs-lookup"><span data-stu-id="404a3-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="404a3-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="404a3-106">To correct this error</span></span>  
  
-   <span data-ttu-id="404a3-107">Найдите и удалите ненужный оператор `Class` .</span><span class="sxs-lookup"><span data-stu-id="404a3-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
-   <span data-ttu-id="404a3-108">В заключение `Class` блок с соответствующим `End Class`.</span><span class="sxs-lookup"><span data-stu-id="404a3-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404a3-109">См. также</span><span class="sxs-lookup"><span data-stu-id="404a3-109">See also</span></span>
- [<span data-ttu-id="404a3-110">Конец \<ключевое слово > инструкции</span><span class="sxs-lookup"><span data-stu-id="404a3-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [<span data-ttu-id="404a3-111">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="404a3-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
