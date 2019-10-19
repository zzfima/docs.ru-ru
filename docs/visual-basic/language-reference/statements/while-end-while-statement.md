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
ms.openlocfilehash: 5da05835998b2e9ef9aeefe5b00faf9e1ecb9ce2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582261"
---
# <a name="whileend-while-statement-visual-basic"></a>Оператор While... End While (Visual Basic)
Выполняет ряд инструкций, если заданное условие имеет `True`.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
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
|`condition`|Обязательный. выражение `Boolean`. Если `condition` `Nothing`, Visual Basic рассматривает его как `False`.|  
|`statements`|Необязательный. Один или несколько инструкций, следующих за `While`, которые выполняются каждый раз, когда `condition` `True`.|  
|`Continue While`|Необязательный. Передает управление следующей итерации блока `While`.|  
|`Exit While`|Необязательный. Передает управление за пределы блока `While`.|  
|`End While`|Обязательный. Завершает определение блока `While`.|  
  
## <a name="remarks"></a>Заметки  
 Используйте структуру `While...End While`, если нужно повторить набор инструкций неопределенное количество раз, пока условие остается `True`. Если вы хотите обеспечить большую гибкость при тестировании условия или результата тестирования, вы можете предпочесть оператору [Do... Loop, инструкция](../../../visual-basic/language-reference/statements/do-loop-statement.md). Если нужно повторить инструкции заданное число раз, то [для... ](../../../visual-basic/language-reference/statements/for-next-statement.md)Обычно лучше подходит следующий оператор.  
  
> [!NOTE]
> Ключевое слово `While` также используется в [инструкции Do... Оператор Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), [предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) и [предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Если `condition` `True`, все `statements` выполняться до тех пор, пока не будет обнаружена инструкция `End While`. Затем управление возвращается к инструкции `While`, а `condition` снова проверяется. Если `condition` по-прежнему `True`, процесс повторяется. Если это `False`, управление передается оператору, который следует за инструкцией `End While`.  
  
 Оператор `While` всегда проверяет условие перед началом цикла. Цикл продолжается, пока условие остается `True`. Если `condition` `False` при первом входе в цикл, он не выполняется даже один раз.  
  
 @No__t_0 обычно является результатом сравнения двух значений, но может быть любым выражением, результатом вычисления которого является [логическое значение типа данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` или `False`). Это выражение может включать значение другого типа данных, такое как числовой тип, преобразованное в `Boolean`.  
  
 Можно вкладывать `While` циклы, помещая один цикл внутрь другого. Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Выйти, пока  
 Оператор [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) может предоставить другой способ выхода из цикла `While`. `Exit While` немедленно передает управление оператору, который следует за инструкцией `End While`.  
  
 Обычно `Exit While` используется после оценки некоторого условия (например, в структуре `If...Then...Else`). Может потребоваться выйти из цикла, если обнаруживается условие, которое делает ненужным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. @No__t_0 можно использовать при проверке условия, которое может вызвать *бесконечный цикл*, то есть цикл, который может выполнять очень большое или даже бесконечное число раз. Затем можно использовать `Exit While` для экранирования цикла.  
  
 В цикле `While` можно поместить любое количество `Exit While` инструкций.  
  
 При использовании внутри вложенных циклов `While` `Exit While` передает управление из самого внутреннего цикла и в следующий более высокий уровень вложенности.  
  
 Оператор `Continue While` немедленно передает управление следующей итерации цикла. Дополнительные сведения см. в разделе [оператор continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере операторы в цикле продолжают выполняться до тех пор, пока значение переменной `index` не превышает 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование инструкций `Continue While` и `Exit While`.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Пример  
 В следующем примере считываются все строки в текстовом файле. Метод <xref:System.IO.File.OpenText%2A> открывает файл и возвращает <xref:System.IO.StreamReader>, который считывает символы. В `While`ном условии <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, содержит ли файл дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>См. также

- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
