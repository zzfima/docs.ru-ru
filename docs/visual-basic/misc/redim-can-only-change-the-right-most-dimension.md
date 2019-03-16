---
title: "\"ReDim\" может изменять только крайнее правое измерение"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 86d639e70e85b19a91f89fa4e0cab330af07dccf
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58028816"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="26ca0-102">"ReDim" может изменять только крайнее правое измерение</span><span class="sxs-lookup"><span data-stu-id="26ca0-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="26ca0-103">В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением.</span><span class="sxs-lookup"><span data-stu-id="26ca0-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="26ca0-104">При использовании `Preserve`можно изменять размер только последнего измерения массива.</span><span class="sxs-lookup"><span data-stu-id="26ca0-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="26ca0-105">Для всех других измерений необходимо указать тот же размер, что и для существующего массива.</span><span class="sxs-lookup"><span data-stu-id="26ca0-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26ca0-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="26ca0-106">To correct this error</span></span>  
  
-   <span data-ttu-id="26ca0-107">Удалите ключевое слово `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="26ca0-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ca0-108">См. также</span><span class="sxs-lookup"><span data-stu-id="26ca0-108">See also</span></span>

- [<span data-ttu-id="26ca0-109">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26ca0-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="26ca0-110">Размерности массивов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26ca0-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="26ca0-111">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="26ca0-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="26ca0-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="26ca0-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
