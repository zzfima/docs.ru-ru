---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 559595e9902ec2f0a19fd6b13e2c89fa1c2b52d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602415"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="d2c5c-102">Оператор Class должен заканчиваться соответствующим End Class</span><span class="sxs-lookup"><span data-stu-id="d2c5c-102">'Class' statement must end with a matching 'End Class'</span></span>
<span data-ttu-id="d2c5c-103">`Class` используется для запуска `Class` block; поэтому он может присутствовать только в начале блока, соответствующий `End Class` инструкции, завершать этот блок.</span><span class="sxs-lookup"><span data-stu-id="d2c5c-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="d2c5c-104">Либо имеется лишний оператор `Class` инструкции, или не заканчивается на `Class` блоке с `End Class`.</span><span class="sxs-lookup"><span data-stu-id="d2c5c-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="d2c5c-105">**Идентификатор ошибки:** BC30481</span><span class="sxs-lookup"><span data-stu-id="d2c5c-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2c5c-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d2c5c-106">To correct this error</span></span>  
  
- <span data-ttu-id="d2c5c-107">Найдите и удалите ненужный оператор `Class` .</span><span class="sxs-lookup"><span data-stu-id="d2c5c-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
- <span data-ttu-id="d2c5c-108">В заключение `Class` блок с соответствующим `End Class`.</span><span class="sxs-lookup"><span data-stu-id="d2c5c-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c5c-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d2c5c-109">See also</span></span>

- [<span data-ttu-id="d2c5c-110">Конец \<ключевое слово > инструкции</span><span class="sxs-lookup"><span data-stu-id="d2c5c-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [<span data-ttu-id="d2c5c-111">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="d2c5c-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
