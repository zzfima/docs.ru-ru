---
title: Предложение Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 84c8f39e632eebbe5382492669820910b38bc360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839747"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="d3cee-102">Предложение Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3cee-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="d3cee-103">Указывает, что внешняя процедура имеет другое имя в файле DLL.</span><span class="sxs-lookup"><span data-stu-id="d3cee-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3cee-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3cee-104">Remarks</span></span>  
 <span data-ttu-id="d3cee-105">`Alias` Слово может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="d3cee-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="d3cee-106">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="d3cee-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="d3cee-107">В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32.dll, `GetUserNameA`, в котором `getUserName` используется вместо параметра в этом примере.</span><span class="sxs-lookup"><span data-stu-id="d3cee-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="d3cee-108">Функция `getUserName` вызывается в sub `getUser`, который отображает имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3cee-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="d3cee-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d3cee-109">See also</span></span>

- [<span data-ttu-id="d3cee-110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d3cee-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
