---
title: В спецификаторах типов не могут задаваться границы массива
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f20ed883005641082eb89e2effa5221594910ffe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838785"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>В спецификаторах типов не могут задаваться границы массива
Размеры массива не могут объявляться как часть спецификатора типа данных.  
  
 **Идентификатор ошибки:** BC30638  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Укажите размер массива сразу после имени переменной, вместо размер массива после типа, как показано в следующем примере.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   Определить массив и инициализировать его с требуемое число элементов, как показано в следующем примере.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>См. также

- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
