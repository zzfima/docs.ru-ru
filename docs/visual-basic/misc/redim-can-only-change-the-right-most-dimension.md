---
title: '&#39;ReDim&#39; можно изменять только крайнее правое измерение'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 94e0fe81f7e750a67943b68f2db700e3a7831da1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502590"
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="638c8-102">&#39;ReDim&#39; можно изменять только крайнее правое измерение</span><span class="sxs-lookup"><span data-stu-id="638c8-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="638c8-103">В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением.</span><span class="sxs-lookup"><span data-stu-id="638c8-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="638c8-104">При использовании `Preserve`можно изменять размер только последнего измерения массива.</span><span class="sxs-lookup"><span data-stu-id="638c8-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="638c8-105">Для всех других измерений необходимо указать тот же размер, что и для существующего массива.</span><span class="sxs-lookup"><span data-stu-id="638c8-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="638c8-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="638c8-106">To correct this error</span></span>  
  
-   <span data-ttu-id="638c8-107">Удалите ключевое слово `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="638c8-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638c8-108">См. также</span><span class="sxs-lookup"><span data-stu-id="638c8-108">See Also</span></span>  
 [<span data-ttu-id="638c8-109">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="638c8-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="638c8-110">Размерности массивов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="638c8-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="638c8-111">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="638c8-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="638c8-112">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="638c8-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="638c8-113">Preserve — удалено</span><span class="sxs-lookup"><span data-stu-id="638c8-113">Preserve - delete</span></span>](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
