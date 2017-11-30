---
title: "Оператор REM (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 Необязательно. Текст комментария, который требуется включить. Пробел требуется между `REM` ключевое слово и `comment`.  
  
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
