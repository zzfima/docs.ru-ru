---
title: В спецификаторах типов не могут задаваться границы массива
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 45787db51de562f2266c587fd2bb15ef29ebefbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583687"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="1dd4c-102">В спецификаторах типов не могут задаваться границы массива</span><span class="sxs-lookup"><span data-stu-id="1dd4c-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="1dd4c-103">Размеры массива не могут объявляться как часть спецификатора типа данных.</span><span class="sxs-lookup"><span data-stu-id="1dd4c-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="1dd4c-104">**Идентификатор ошибки:** BC30638</span><span class="sxs-lookup"><span data-stu-id="1dd4c-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1dd4c-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1dd4c-105">To correct this error</span></span>  
  
-   <span data-ttu-id="1dd4c-106">Укажите размер массива сразу после имени переменной, вместо размера массива после типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1dd4c-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="1dd4c-107">Определить массив и инициализируйте его с требуемое число элементов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="1dd4c-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1dd4c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1dd4c-108">See Also</span></span>  
 [<span data-ttu-id="1dd4c-109">Массивы</span><span class="sxs-lookup"><span data-stu-id="1dd4c-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
