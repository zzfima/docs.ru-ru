---
title: Предложение Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 62b34f5860b35104b6a8caa82c359383999dd61b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599178"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="3eff7-102">Предложение Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3eff7-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="3eff7-103">Указывает, что внешняя процедура имеет другое имя в файле DLL.</span><span class="sxs-lookup"><span data-stu-id="3eff7-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eff7-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="3eff7-104">Remarks</span></span>  
 <span data-ttu-id="3eff7-105">`Alias` Ключевое слово может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="3eff7-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="3eff7-106">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="3eff7-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="3eff7-107">В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32.dll, `GetUserNameA`, которая `getUserName` используется вместо в этом примере.</span><span class="sxs-lookup"><span data-stu-id="3eff7-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="3eff7-108">Функция `getUserName` вызывается в sub `getUser`, который отображает имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3eff7-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3eff7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3eff7-109">See Also</span></span>  
 [<span data-ttu-id="3eff7-110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3eff7-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
