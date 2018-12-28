---
title: ReDim не может изменять размерность
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: ba3e389e3732d39f16e2c8ae884fae4e935e6ac9
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2018
ms.locfileid: "53778727"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="88bf6-102">ReDim не может изменять размерность</span><span class="sxs-lookup"><span data-stu-id="88bf6-102">'ReDim' cannot change the number of dimensions</span></span>
<span data-ttu-id="88bf6-103">Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива.</span><span class="sxs-lookup"><span data-stu-id="88bf6-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="88bf6-104">Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.</span><span class="sxs-lookup"><span data-stu-id="88bf6-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88bf6-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="88bf6-105">To correct this error</span></span>  
  
-   <span data-ttu-id="88bf6-106">Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.</span><span class="sxs-lookup"><span data-stu-id="88bf6-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88bf6-107">См. также</span><span class="sxs-lookup"><span data-stu-id="88bf6-107">See Also</span></span>  
 [<span data-ttu-id="88bf6-108">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88bf6-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="88bf6-109">Размерности массивов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88bf6-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="88bf6-110">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="88bf6-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="88bf6-111">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="88bf6-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
