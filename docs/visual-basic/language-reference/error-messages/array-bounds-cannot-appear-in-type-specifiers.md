---
title: В спецификаторах типов не могут задаваться границы массива
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="8bc60-102">В спецификаторах типов не могут задаваться границы массива</span><span class="sxs-lookup"><span data-stu-id="8bc60-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="8bc60-103">Размеры массива не могут объявляться как часть спецификатора типа данных.</span><span class="sxs-lookup"><span data-stu-id="8bc60-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="8bc60-104">**Идентификатор ошибки:** BC30638</span><span class="sxs-lookup"><span data-stu-id="8bc60-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8bc60-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8bc60-105">To correct this error</span></span>  
  
-   <span data-ttu-id="8bc60-106">Укажите размер массива сразу после имени переменной, вместо размера массива после типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bc60-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="8bc60-107">Определить массив и инициализируйте его с требуемое число элементов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bc60-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8bc60-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8bc60-108">See Also</span></span>  
 [<span data-ttu-id="8bc60-109">Массивы</span><span class="sxs-lookup"><span data-stu-id="8bc60-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
