---
title: '&#39; ReDim &#39; не может изменять число измерений'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cf3713c72bd07803935065780e894c130911a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="c6a51-102">&#39; ReDim &#39; не может изменять число измерений</span><span class="sxs-lookup"><span data-stu-id="c6a51-102">&#39;ReDim&#39; cannot change the number of dimensions</span></span>
<span data-ttu-id="c6a51-103">Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива.</span><span class="sxs-lookup"><span data-stu-id="c6a51-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="c6a51-104">Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.</span><span class="sxs-lookup"><span data-stu-id="c6a51-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6a51-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c6a51-105">To correct this error</span></span>  
  
-   <span data-ttu-id="c6a51-106">Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.</span><span class="sxs-lookup"><span data-stu-id="c6a51-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a51-107">См. также</span><span class="sxs-lookup"><span data-stu-id="c6a51-107">See Also</span></span>  
 [<span data-ttu-id="c6a51-108">Массивы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c6a51-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="c6a51-109">Размерности массивов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c6a51-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="c6a51-110">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="c6a51-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="c6a51-111">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="c6a51-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
