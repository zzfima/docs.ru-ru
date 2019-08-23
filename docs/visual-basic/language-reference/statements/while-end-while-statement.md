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
ms.openlocfilehash: 7ea0814c587f65ddc1f114d2314ac7147143d40d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965816"
---
# <a name="whileend-while-statement-visual-basic"></a>Оператор While... End While (Visual Basic)
Выполняет последовательность операторов, если заданное условие имеет значение `True`.  
  
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
|`condition`|Обязательный. `Boolean`выражение. Если `condition` имеет `Nothing`значение, Visual Basic обрабатывает его `False`как.|  
|`statements`|Необязательный параметр. Один или несколько следующих `While`инструкций, которые выполняются каждый раз `condition` , —. `True`|  
|`Continue While`|Необязательный параметр. Передает управление следующей итерации `While` блока.|  
|`Exit While`|Необязательный параметр. Передает управление за пределы `While` блока.|  
|`End While`|Обязательный. Завершает определение блока `While`.|  
  
## <a name="remarks"></a>Примечания  
 Используйте структуру, если необходимо повторить набор инструкций неопределенное количество раз, если условие остается `True`. `While...End While` Если вы хотите обеспечить большую гибкость при тестировании условия или результата тестирования, вы можете предпочесть оператору [Do... Loop, инструкция](../../../visual-basic/language-reference/statements/do-loop-statement.md). Если нужно повторить инструкции заданное число раз, то [для... ](../../../visual-basic/language-reference/statements/for-next-statement.md)Обычно лучше подходит следующий оператор.  
  
> [!NOTE]
> `While` Ключевое слово также используется в [инструкции Do... Оператор Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), [предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) и [предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Если `condition` имеет `True`значение, все `statements` выполняется до тех пор `End While` , пока не будет обнаружен оператор. Затем элемент управления возвращается в `While` инструкцию и `condition` снова проверяется. Если `condition` по- `True`прежнему, процесс повторяется. Если это `False`так, управление передается оператору, `End While` следующему за оператором.  
  
 `While` Оператор всегда проверяет условие перед началом цикла. Цикл продолжается, пока условие остается `True`. Если `condition` параметр `False` имеет значение при первом входе в цикл, он не выполняется даже один раз.  
  
 Обычно результат сравнения двух значений, но может быть любым выражением, результатом вычисления которого является [логическое значение типа данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` или `False`). `condition` Это выражение может включать в себя значение другого типа данных, например числовой тип, который был преобразован в `Boolean`.  
  
 Можно вложить `While` циклы, поместив один цикл в другой. Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Выйти, пока  
 Оператор [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) может предоставить другой способ выхода из `While` цикла. `Exit While`немедленно передает управление оператору, который следует за `End While` оператором.  
  
 Обычно используется `Exit While` после вычисления некоторого условия (например, `If...Then...Else` в структуре). Может потребоваться выйти из цикла, если обнаруживается условие, которое делает ненужным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Можно использовать `Exit While` при проверке условия, которое может вызвать бесконечный *цикл*, что является циклом, который может выполнять очень большое или даже бесконечное число раз. Затем можно использовать `Exit While` для экранирования цикла.  
  
 Любое количество `Exit While` операторов можно разместить `While` в любом месте цикла.  
  
 При использовании внутри вложенных `While` `Exit While` циклов передает управление за пределы самого внутреннего цикла и в следующий более высокий уровень вложенности.  
  
 `Continue While` Оператор немедленно передает управление следующей итерации цикла. Дополнительные сведения см. в разделе [оператор continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере операторы в цикле продолжают выполняться до тех пор, пока `index` переменная не будет больше 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование `Continue While` операторов и. `Exit While`  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Пример  
 В следующем примере считываются все строки в текстовом файле. Метод открывает файл и возвращает объект <xref:System.IO.StreamReader> , считывающий символы. <xref:System.IO.File.OpenText%2A> В условии <xref:System.IO.StreamReader.Peek%2A> метод`StreamReader` определяет, содержит ли файл дополнительные символы. `While`  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>См. также

- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)
