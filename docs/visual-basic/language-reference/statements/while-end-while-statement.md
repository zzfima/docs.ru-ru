---
title: Оператор While... End While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 9f46a6ec65faef4448bdd25e30a6cc0c605cd0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604735"
---
# <a name="whileend-while-statement-visual-basic"></a>Оператор While... End While (Visual Basic)
Выполняет последовательность операторов, пока заданное условие является `True`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`condition`|Обязательно. `Boolean` Выражение. Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.|  
|`statements`|Необязательный. Один или несколько следующих инструкций `While`, который запускаться при каждом `condition` — `True`.|  
|`Continue While`|Необязательный. Передает управление следующей итерации цикла `While` блока.|  
|`Exit While`|Необязательный. Передает управление из `While` блока.|  
|`End While`|Обязательно. Завершает определение блока `While`.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `While...End While` структуры, если вы хотите повторить набор инструкций на неопределенное количество раз, до тех пор, пока условие остается `True`. Если требуется больше гибкости, с которой проверки того, что или результат можно проверить его, может потребоваться [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md). Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.  
  
> [!NOTE]
>  `While` Также используется ключевое слово в [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md), [предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) и [предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Если `condition` — `True`, все из `statements` выполнения до `End While` инструкции. Затем возвращается на управления `While` инструкции и `condition` проверяется заново. Если `condition` по-прежнему `True`, процесс повторяется. Если у него есть `False`, управление передается оператору, следующему `End While` инструкции.  
  
 `While` Оператор всегда проверяет условие перед началом цикла. Выполнение цикла продолжается, пока значение условия равно `True`. Если `condition` — `False` при первом входе цикла, он не запускается даже один раз.  
  
 `condition` Обычно результатом сравнения двух значений, но может быть любое выражение, результатом которого является [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`). Это выражение может включать значение другого типа данных, например числовой тип, который был преобразован в `Boolean`.  
  
 Можно вложить `While` циклы, поместив один в другой. Также можно вложить различные виды структур управления друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Выход при  
 [Выхода во время](../../../visual-basic/language-reference/statements/exit-statement.md) инструкции можно предоставить другим способом, чтобы выйти из `While` цикла. `Exit While` немедленно передает управление оператору, следующему `End While` инструкции.  
  
 Как правило, используется `Exit While` после вычисления некоторого условия (например, в `If...Then...Else` структуры). Может потребоваться выйти из цикла при обнаружении условия, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Можно использовать `Exit While` при проверке условия, которое может привести к *бесконечный цикл*, который является цикл, который может запустить слишком большой или возможно, бесконечное число раз. Затем можно использовать `Exit While` для выхода из цикла.  
  
 Можно установить любое число `Exit While` инструкций в любом месте в `While` цикла.  
  
 При использовании внутри вложенной `While` циклы, `Exit While` передает управление из самого внутреннего цикла и отправляются верхнего уровня вложенности.  
  
 `Continue While` Инструкция немедленно передает управление следующей итерации цикла. Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере инструкции в цикле по-прежнему выполняются, пока `index` переменной больше 10.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует использование `Continue While` и `Exit While` инструкции.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример считывает все строки в текстовом файле. <xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы. В `While` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, содержит ли файл дополнительных символов.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a>См. также  
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
