---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 0619db618abd562bda86836bdd41bbcd6caee0f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836510"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="d2e24-102">Оператор Class должен заканчиваться соответствующим End Class</span><span class="sxs-lookup"><span data-stu-id="d2e24-102">'Class' statement must end with a matching 'End Class'</span></span>
<span data-ttu-id="d2e24-103">`Class` используется для запуска `Class` block; поэтому он может присутствовать только в начале блока, соответствующий `End Class` инструкции, завершать этот блок.</span><span class="sxs-lookup"><span data-stu-id="d2e24-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="d2e24-104">Либо имеется лишний оператор `Class` инструкции, или не заканчивается на `Class` блоке с `End Class`.</span><span class="sxs-lookup"><span data-stu-id="d2e24-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="d2e24-105">**Идентификатор ошибки:** BC30481</span><span class="sxs-lookup"><span data-stu-id="d2e24-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2e24-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d2e24-106">To correct this error</span></span>  
  
-   <span data-ttu-id="d2e24-107">Найдите и удалите ненужный оператор `Class` .</span><span class="sxs-lookup"><span data-stu-id="d2e24-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
-   <span data-ttu-id="d2e24-108">В заключение `Class` блок с соответствующим `End Class`.</span><span class="sxs-lookup"><span data-stu-id="d2e24-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e24-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d2e24-109">See also</span></span>

- [<span data-ttu-id="d2e24-110">Конец \<ключевое слово > инструкции</span><span class="sxs-lookup"><span data-stu-id="d2e24-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [<span data-ttu-id="d2e24-111">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="d2e24-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
