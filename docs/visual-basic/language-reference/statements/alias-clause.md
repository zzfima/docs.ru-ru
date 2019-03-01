---
title: Предложение Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 3b1a66ecfd3c023a12ac62191ca3671a195b45a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978232"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="b641f-102">Предложение Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b641f-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="b641f-103">Указывает, что внешняя процедура имеет другое имя в файле DLL.</span><span class="sxs-lookup"><span data-stu-id="b641f-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b641f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="b641f-104">Remarks</span></span>  
 <span data-ttu-id="b641f-105">`Alias` Слово может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="b641f-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="b641f-106">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="b641f-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="b641f-107">В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32.dll, `GetUserNameA`, в котором `getUserName` используется вместо параметра в этом примере.</span><span class="sxs-lookup"><span data-stu-id="b641f-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="b641f-108">Функция `getUserName` вызывается в sub `getUser`, который отображает имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="b641f-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="b641f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b641f-109">See also</span></span>
- [<span data-ttu-id="b641f-110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b641f-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
