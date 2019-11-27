---
title: Оператор REM
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
ms.openlocfilehash: bdde4beae242c3175b02cd2af252babb850416f6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346731"
---
# <a name="rem-statement-visual-basic"></a>Оператор REM (Visual Basic)
Используется для включения пояснительных примечаний в исходный код программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Части  
 `comment`  
 Необязательный элемент. Текст любого комментария, который требуется включить. Между ключевым словом `REM` и `comment`требуется пробел.  
  
## <a name="remarks"></a>Примечания  
 Инструкцию `REM` можно добавить только в строку или вставить в строку, следующую за другой инструкцией. Оператор `REM` должен быть последним оператором в строке. Если он соответствует другому оператору, `REM` должен быть отделен от этого оператора пробелами.  
  
 Вместо `REM`можно использовать одиночную кавычку (`'`). Это верно, если ваш комментарий следует другому оператору в той же строке или расподержаться только в строке.  
  
> [!NOTE]
> Нельзя продолжить инструкцию `REM` с помощью последовательности продолжения строки (`_`). После начала комментария компилятор не проверяет символы на предмет особого значения. Для многострочного комментария используйте другой оператор `REM` или символ комментария (`'`) в каждой строке.  
  
## <a name="example"></a>Пример  
 В следующем примере показана инструкция `REM`, которая используется для включения пояснительных примечаний в программу. Кроме того, в нем показано использование одинарной кавычки (`'`) вместо `REM`.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Комментарии в коде](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
