---
title: Оператор Do…Loop
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 9384cbb355189be448fa4b8d274721b4a7ca6a20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351253"
---
# <a name="doloop-statement-visual-basic"></a>Оператор Do...Loop (Visual Basic)
Повторяет блок инструкций, пока `Boolean` условие `True` или пока условие не станет `True`.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`Do`|Обязательно. Запускает определение цикла `Do`.|  
|`While`|Является обязательным, если используется параметр `Until`. Повторите цикл, пока `condition` не `False`.|  
|`Until`|Является обязательным, если используется параметр `While`. Повторите цикл, пока `condition` не `True`.|  
|`condition`|Необязательный элемент. выражение `Boolean`. Если `condition` `Nothing`, Visual Basic рассматривает его как `False`.|  
|`statements`|Необязательный элемент. Одна или несколько инструкций, которые повторяются, или до, `condition` `True`.|  
|`Continue Do`|Необязательный элемент. Передает управление следующей итерации цикла `Do`.|  
|`Exit Do`|Необязательный элемент. Передает управление за пределы цикла `Do`.|  
|`Loop`|Обязательно. Завершает определение цикла `Do`.|  
  
## <a name="remarks"></a>Примечания  
 Используйте структуру `Do...Loop`, если нужно повторить набор инструкций неопределенное число раз, пока не будет удовлетворено условие. Если нужно повторить инструкции заданное число раз, то [для... ](../../../visual-basic/language-reference/statements/for-next-statement.md)Обычно лучше подходит следующий оператор.  
  
 Можно использовать либо `While`, либо `Until`, чтобы указать `condition`, но не оба.  
  
 `condition` можно тестировать только один раз, в начале или в конце цикла. Если протестировать `condition` в начале цикла (в инструкции `Do`), цикл может не выполняться даже один раз. При проверке в конце цикла (в операторе `Loop`) цикл всегда выполняется по крайней мере один раз.  
  
 Условие обычно является результатом сравнения двух значений, но может быть любым выражением, результатом вычисления которого является [логическое значение типа данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` или `False`). Сюда относятся значения других типов данных, например числовые типы, которые были преобразованы в `Boolean`.  
  
 Можно вкладывать `Do` циклы, помещая один цикл внутрь другого. Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
> Структура `Do...Loop` обеспечивает большую гибкость, чем [while... Оператор End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , так как он позволяет решить, следует ли завершать цикл, когда `condition` останавливается `True` или когда он сначала превращается в `True`. Он также позволяет тестировать `condition` как в начале, так и в конце цикла.  
  
## <a name="exit-do"></a>Выйти  
 Оператор [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) может предоставить альтернативный способ выхода из `Do…Loop`. `Exit Do` немедленно передает управление оператору, который следует за инструкцией `Loop`.  
  
 `Exit Do` часто используется после оценки какого-либо условия, например в структуре `If...Then...Else`. Может потребоваться выйти из цикла, если обнаруживается условие, которое делает ненужным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Одним из способов использования `Exit Do` является проверка условия, которое может вызвать *бесконечный цикл*, то есть цикл, который может выполнять большое или даже бесконечное число раз. Для экранирования цикла можно использовать `Exit Do`.  
  
 В `Do…Loop`можно включить любое количество `Exit Do` инструкций.  
  
 При использовании внутри вложенных циклов `Do` `Exit Do` передает управление из самого внутреннего цикла и в следующий более высокий уровень вложенности.  
  
## <a name="example"></a>Пример  
 В следующем примере операторы в цикле продолжают выполняться до тех пор, пока значение переменной `index` не превышает 10. Предложение `Until` находится в конце цикла.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Пример  
 В следующем примере вместо предложения `Until` используется предложение `While`, а `condition` проверяется в начале цикла, а не в конце.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Пример  
 В следующем примере `condition` останавливает цикл, если `index`ая переменная больше 100. Однако оператор `If` в цикле приводит к тому, что инструкция `Exit Do` останавливает цикл, когда переменная индекса больше 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Пример  
 В следующем примере считываются все строки в текстовом файле. Метод <xref:System.IO.File.OpenText%2A> открывает файл и возвращает <xref:System.IO.StreamReader>, который считывает символы. В `Do...Loop`ном условии <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, есть ли дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>См. также

- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
