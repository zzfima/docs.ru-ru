---
title: Оператор REM (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 3bd526b08e1ba3be856e1e823cf8ef49ea9b6c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="rem-statement-visual-basic"></a>Оператор REM (Visual Basic)
Используется для включения поясняющий текст в исходном коде программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Части  
 `comment`  
 Необязательный. Текст комментария, который требуется включить. Пробел требуется между `REM` ключевое слово и `comment`.  
  
## <a name="remarks"></a>Примечания  
 Можно поместить `REM` инструкции только в строке, или можно поместить в строке за другим оператором. `REM` Инструкция должна быть последней инструкцией в строке. За инструкцией, `REM` должно отделяться от этого оператора пробелом.  
  
 Можно использовать одинарную кавычку (`'`) вместо `REM`. Это верно ли примечания, следующего за другим оператором в той же строке, и примечания, занимающего всю строку.  
  
> [!NOTE]
>  Не удается продолжить `REM` инструкции можно использовать последовательность продолжения строки (`_`). После начала, компилятор не проверяет символы для особое значение. Для многострочных комментариев, используйте другой `REM` оператор или символ комментария (`'`) в каждой строке.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется `REM` инструкцию, которая используется для включения пояснения в программе. Он также демонстрируется использование символа одинарной кавычки (`'`) вместо `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Комментарии в коде](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
