---
title: Количество индексов превышает размерность индексированного массива
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 01659205f271b089fe4e8aa87cf7a8c44e7a4000
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837998"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="4bfb9-102">Количество индексов превышает размерность индексированного массива</span><span class="sxs-lookup"><span data-stu-id="4bfb9-102">Number of indices exceeds the number of dimensions of the indexed array</span></span>
<span data-ttu-id="4bfb9-103">Число индексов, используемых для доступа к элементу массива, должно быть точно равно рангу массива, то есть числу измерений, объявленных для него.</span><span class="sxs-lookup"><span data-stu-id="4bfb9-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>  
  
 <span data-ttu-id="4bfb9-104">**Идентификатор ошибки:** BC30106</span><span class="sxs-lookup"><span data-stu-id="4bfb9-104">**Error ID:** BC30106</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4bfb9-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4bfb9-105">To correct this error</span></span>  
  
-   <span data-ttu-id="4bfb9-106">Удалите индексы из ссылки на массив общего количества индексов с рангом массива.</span><span class="sxs-lookup"><span data-stu-id="4bfb9-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="4bfb9-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="4bfb9-107">For example:</span></span>  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4bfb9-108">См. также</span><span class="sxs-lookup"><span data-stu-id="4bfb9-108">See also</span></span>

- [<span data-ttu-id="4bfb9-109">Массивы</span><span class="sxs-lookup"><span data-stu-id="4bfb9-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
