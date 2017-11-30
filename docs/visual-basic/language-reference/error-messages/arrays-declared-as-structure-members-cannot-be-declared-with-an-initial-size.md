---
title: "Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords: BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 983154a144a79991c86db5056ad0e0e563a3ba73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
