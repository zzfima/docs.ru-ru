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
ms.openlocfilehash: a3ad63472f6a3f7ae1ec13742185790667c7bcf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699055"
---
# <a name="rem-statement-visual-basic"></a>Оператор REM (Visual Basic)
Используется для включения поясняющими замечаниями в исходном коде программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Части  
 `comment`  
 Необязательный параметр. Текст комментария, которые вы хотите включить. Пробел между `REM` ключевое слово и `comment`.  
  
## <a name="remarks"></a>Примечания  
 Вы можете поместить `REM` инструкции только в строке, или вы можете поместить его в строке после другого оператора. `REM` Инструкция должна быть последней инструкцией в строке. За другого оператора, `REM` должен отделяться от этого оператора пробелом.  
  
 Можно использовать одинарную кавычку (`'`) вместо `REM`. Это верно ли ваш комментарий после другого оператора в той же строке или примечания, занимающего всю строку.  
  
> [!NOTE]
>  Не удается продолжить `REM` инструкции с помощью последовательности продолжения строки (`_`). После начала, компилятор не проверяет символы для специального значения. Для многострочных комментариев, используйте другой `REM` оператор или символ комментария (`'`) в каждой строке.  
  
## <a name="example"></a>Пример  
 В следующем примере показано `REM` инструкцию, которая используется для включения поясняющими замечаниями в программе. Он также демонстрируется использование символа одинарной кавычки (`'`) вместо `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>См. также
- [Комментарии в коде](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
