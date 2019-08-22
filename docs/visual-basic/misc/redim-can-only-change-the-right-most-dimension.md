---
title: "\"ReDim\" может изменять только крайнее правое измерение"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: f38bcb99b682ace497859b67fe3bb829bbc80c4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664406"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="cd7ef-102">"ReDim" может изменять только крайнее правое измерение</span><span class="sxs-lookup"><span data-stu-id="cd7ef-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="cd7ef-103">В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением.</span><span class="sxs-lookup"><span data-stu-id="cd7ef-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="cd7ef-104">При использовании `Preserve`можно изменять размер только последнего измерения массива.</span><span class="sxs-lookup"><span data-stu-id="cd7ef-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="cd7ef-105">Для всех других измерений необходимо указать тот же размер, что и для существующего массива.</span><span class="sxs-lookup"><span data-stu-id="cd7ef-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd7ef-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cd7ef-106">To correct this error</span></span>  
  
- <span data-ttu-id="cd7ef-107">Удалите ключевое слово `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="cd7ef-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7ef-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cd7ef-108">See also</span></span>

- [<span data-ttu-id="cd7ef-109">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd7ef-109">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="cd7ef-110">Размеры массива в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cd7ef-110">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="cd7ef-111">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="cd7ef-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="cd7ef-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="cd7ef-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
