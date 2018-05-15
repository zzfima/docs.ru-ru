---
title: '&#39;Оператор reDim&#39; можно изменять только крайнее правое измерение'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: efb98df13a7e3e378347b30b6fc00b90030ec194
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="86c80-102">&#39;Оператор reDim&#39; можно изменять только крайнее правое измерение</span><span class="sxs-lookup"><span data-stu-id="86c80-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="86c80-103">В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением.</span><span class="sxs-lookup"><span data-stu-id="86c80-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="86c80-104">При использовании `Preserve`можно изменять размер только последнего измерения массива.</span><span class="sxs-lookup"><span data-stu-id="86c80-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="86c80-105">Для всех других измерений необходимо указать тот же размер, что и для существующего массива.</span><span class="sxs-lookup"><span data-stu-id="86c80-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86c80-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="86c80-106">To correct this error</span></span>  
  
-   <span data-ttu-id="86c80-107">Удалите ключевое слово `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="86c80-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c80-108">См. также</span><span class="sxs-lookup"><span data-stu-id="86c80-108">See Also</span></span>  
 [<span data-ttu-id="86c80-109">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86c80-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="86c80-110">Размерности массивов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86c80-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="86c80-111">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="86c80-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="86c80-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="86c80-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="86c80-113">Preserve — удалить</span><span class="sxs-lookup"><span data-stu-id="86c80-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
