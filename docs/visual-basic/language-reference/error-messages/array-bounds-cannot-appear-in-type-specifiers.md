---
title: "В спецификаторах типов не могут задаваться границы массива"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords: BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
