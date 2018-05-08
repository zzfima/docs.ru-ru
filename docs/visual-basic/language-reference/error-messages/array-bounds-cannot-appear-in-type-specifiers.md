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
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>В спецификаторах типов не могут задаваться границы массива
Размеры массива не могут объявляться как часть спецификатора типа данных.  
  
 **Идентификатор ошибки:** BC30638  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Укажите размер массива сразу после имени переменной, вместо размера массива после типа, как показано в следующем примере.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   Определить массив и инициализируйте его с требуемое число элементов, как показано в следующем примере.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>См. также  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
