---
title: Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 0a7424e5dbfadd78c4071ba5b76086b7f6c9b94a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585857"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера
Массив в структуре объявлен с указанием начального размера. Не удается инициализировать любой элемент структуры и объявить размер массива является одной форме инициализации.  
  
 **Идентификатор ошибки:** BC31043  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите массив в структуре как динамический (без указания начального размера).  
  
2.  Если требуется, чтобы размер массива, можно использовать преобразование динамического массива с [оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) при выполнении кода. Это показано в следующем примере.  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a>См. также  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Практическое руководство. Объявление структуры](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
