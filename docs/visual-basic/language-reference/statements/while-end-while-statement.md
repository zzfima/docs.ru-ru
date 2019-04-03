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
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843717"
---
# <a name="whileend-while-statement-visual-basic"></a>Оператор While... End While (Visual Basic)
Выполняет ряд инструкций до тех пор, пока заданное условие является `True`.  
  
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
|`condition`|Обязательный. `Boolean` выражение. Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.|  
|`statements`|Необязательный параметр. Один или несколько следующих инструкций `While`, который запускаться при каждом `condition` является `True`.|  
|`Continue While`|Необязательный параметр. Передает управление следующей итерации `While` блока.|  
|`Exit While`|Необязательный параметр. Передает управление из `While` блока.|  
|`End While`|Обязательный. Завершает определение блока `While`.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `While...End While` структуры, когда нужно повторить набор инструкций неограниченное число раз, до тех пор, пока условие остается `True`. Если требуется более гибкое и где проверить условие или результат можно проверить его, может потребоваться [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md). Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.  
  
> [!NOTE]
>  `While` Ключевое слово также используется в [сделать... Цикл инструкции](../../../visual-basic/language-reference/statements/do-loop-statement.md), [предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) и [предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Если `condition` — `True`, все из `statements` выполнения до `End While` встречается. Элемент управления затем возвращается на `While` инструкции и `condition` проверяется заново. Если `condition` по-прежнему `True`, этот процесс повторяется. Если у него есть `False`, управление передается оператору, который расположен `End While` инструкции.  
  
 `While` Оператор всегда проверяет условие перед началом цикла. Выполнение цикла продолжается, пока значение условия равно `True`. Если `condition` является `False` при первом входе в цикл, оно вообще не запускается.  
  
 `condition` Обычно результаты из сравнения двух значений, но он может быть любое выражение, результатом которого является [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`). Это выражение может включать значение другого типа данных, таких как числовой тип, который был преобразован в `Boolean`.  
  
 Можно вложить `While` циклы, поместив один внутри другого. Можно также вложить разные виды структур управления друг с другом. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Выход при  
 [Выйти из во время](../../../visual-basic/language-reference/statements/exit-statement.md) инструкции можно найти другой способ выхода из `While` цикла. `Exit While` немедленно передает управление оператору, который расположен `End While` инструкции.  
  
 Как правило, используется `Exit While` после вычисления некоторого условия (например, в `If...Then...Else` структуры). Может потребоваться выйти из цикла, если определяет условие, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Можно использовать `Exit While` при проверке условия, которое может привести к *бесконечный цикл*, который является цикл, который может запустить слишком большой или возможно, бесконечное число раз. Затем можно использовать `Exit While` для выхода из цикла.  
  
 Можно установить любое число `Exit While` инструкций в любом месте в `While` цикла.  
  
 При использовании внутри вложенной `While` циклы, `Exit While` передает управление из самого внутреннего цикла и поместить в следующий уровень вложенности.  
  
 `Continue While` Оператор сразу же передает управление следующей итерации цикла. Дополнительные сведения см. в разделе [оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере операторы в цикле продолжать выполняться до `index` переменной превышает 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует использование `Continue While` и `Exit While` инструкций.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Пример  
 В следующем примере считываются все строки в текстовом файле. <xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы. В `While` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, содержит ли файл, дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>См. также

- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
