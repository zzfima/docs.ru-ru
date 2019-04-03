---
title: Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 58889809b3d8d0823784279c421a141dc8056984
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841970"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера
Массив в структуре объявлена с начальным размером. Не удается инициализировать любой элемент структуры и объявить размер массива является одним из инициализации.  
  
 **Идентификатор ошибки:** BC31043  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите массив в структуре как динамический (без указания начального размера).  
  
2.  Если вам требуется определенного размера массива, можно изменить размер динамического массива с [оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) когда ваш код выполняется. Это показано в следующем примере.  
  
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

- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Практическое руководство. Объявление структуры](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
