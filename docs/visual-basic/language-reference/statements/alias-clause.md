---
title: Предложение Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: a7f67224c5d26816bdc1974dc4aa82d796c41284
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349150"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="eb8df-102">Предложение Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb8df-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="eb8df-103">Указывает, что у внешней процедуры есть другое имя в своей библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="eb8df-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb8df-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb8df-104">Remarks</span></span>  
 <span data-ttu-id="eb8df-105">В этом контексте можно использовать ключевое слово `Alias`:</span><span class="sxs-lookup"><span data-stu-id="eb8df-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="eb8df-106">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="eb8df-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="eb8df-107">В следующем примере ключевое слово `Alias` используется для предоставления имени функции в advapi32. dll, `GetUserNameA`, которая `getUserName` используется вместо в этом примере.</span><span class="sxs-lookup"><span data-stu-id="eb8df-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="eb8df-108">Функция `getUserName` вызывается в под`getUser`, которая отображает имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="eb8df-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="eb8df-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb8df-109">See also</span></span>

- [<span data-ttu-id="eb8df-110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="eb8df-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
