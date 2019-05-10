---
title: В спецификаторах типов не могут задаваться границы массива
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 50e1cd0e41da467a9e816c8e5d64d09a36923d65
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665737"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>В спецификаторах типов не могут задаваться границы массива
Размеры массива не могут объявляться как часть спецификатора типа данных.  
  
 **Идентификатор ошибки:** BC30638  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Укажите размер массива сразу после имени переменной, вместо размер массива после типа, как показано в следующем примере.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
- Определить массив и инициализировать его с требуемое число элементов, как показано в следующем примере.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>См. также

- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
