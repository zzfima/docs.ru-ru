---
title: Предложение Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 9cf97402d0b0a6cd16dd75a970c1d29a2fcc30a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498574"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="2dde6-102">Предложение Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dde6-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="2dde6-103">Указывает, что внешняя процедура имеет другое имя в файле DLL.</span><span class="sxs-lookup"><span data-stu-id="2dde6-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dde6-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="2dde6-104">Remarks</span></span>  
 <span data-ttu-id="2dde6-105">`Alias` Слово может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="2dde6-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="2dde6-106">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="2dde6-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="2dde6-107">В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32.dll, `GetUserNameA`, в котором `getUserName` используется вместо параметра в этом примере.</span><span class="sxs-lookup"><span data-stu-id="2dde6-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="2dde6-108">Функция `getUserName` вызывается в sub `getUser`, который отображает имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2dde6-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2dde6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2dde6-109">See also</span></span>
- [<span data-ttu-id="2dde6-110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2dde6-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
