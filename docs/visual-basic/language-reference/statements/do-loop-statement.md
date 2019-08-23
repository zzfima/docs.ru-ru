---
title: Оператор Do...Loop (Visual Basic)
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
ms.openlocfilehash: 75a2129a9f332024831d97021e381f1b3d4fa048
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943000"
---
# <a name="doloop-statement-visual-basic"></a>Оператор Do...Loop (Visual Basic)
Повторяет блок инструкций, пока `Boolean` условие находится в состоянии или до тех пор, пока условие не `True` станет `True`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
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
|`Do`|Обязательный. Запускает определение `Do` цикла.|  
|`While`|Является обязательным, если используется параметр `Until`. Повторите цикл, пока `condition` не `False`будет.|  
|`Until`|Является обязательным, если используется параметр `While`. Повторите цикл, пока `condition` не `True`будет.|  
|`condition`|Необязательный параметр. `Boolean`выражение. Если `condition` имеет `Nothing`значение, Visual Basic обрабатывает его `False`как.|  
|`statements`|Необязательный параметр. Одна или несколько инструкций, повторяемых в, или до, `condition` имеют `True`.|  
|`Continue Do`|Необязательный параметр. Передает управление следующей итерации `Do` цикла.|  
|`Exit Do`|Необязательный параметр. Передает управление за пределы `Do` цикла.|  
|`Loop`|Обязательный. Завершает определение `Do` цикла.|  
  
## <a name="remarks"></a>Примечания  
 `Do...Loop` Используйте структуру, если нужно повторить набор инструкций неопределенное число раз, пока не будет удовлетворено условие. Если нужно повторить инструкции заданное число раз, то [для... ](../../../visual-basic/language-reference/statements/for-next-statement.md)Обычно лучше подходит следующий оператор.  
  
 Можно использовать либо `While` `Until` , либо, чтобы `condition`указать, но не оба.  
  
 Тест `condition` можно выполнять только один раз, в начале или в конце цикла. Если проверка `condition` выполняется в начале цикла ( `Do` в операторе), цикл может не выполняться даже один раз. Если протестировать в конце цикла (в `Loop` операторе), цикл всегда выполняется по крайней мере один раз.  
  
 Условие обычно является результатом сравнения двух значений, но может быть любым выражением, результатом вычисления которого является [логическое значение типа данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` или `False`). Сюда относятся значения других типов данных, например числовые типы, которые были преобразованы в `Boolean`.  
  
 Можно вложить `Do` циклы, поместив один цикл в другой. Можно также вкладывать различные виды управляющих структур друг в друга. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
> Эта `Do...Loop` структура обеспечивает большую гибкость, чем [while... Оператор End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , так как он позволяет решить, следует ли завершать цикл `condition` при остановке `True` или при первом преобразовании `True`. Он также позволяет тестироваться `condition` как в начале, так и в конце цикла.  
  
## <a name="exit-do"></a>Выйти  
 Оператор [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) может предоставить альтернативный способ выхода `Do…Loop`из. `Exit Do`немедленно передает управление оператору, следующему за `Loop` оператором.  
  
 `Exit Do`часто используется после вычисления некоторого условия, например в `If...Then...Else` структуре. Может потребоваться выйти из цикла, если обнаруживается условие, которое делает ненужным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Одно из `Exit Do` них — проверка на наличие условия, которое может вызвать бесконечный *цикл*, то есть цикл, который может выполнять большое или даже бесконечное число раз. Для экранирования `Exit Do` цикла можно использовать.  
  
 В можно включить любое количество `Exit Do` операторов в любом месте. `Do…Loop`  
  
 При использовании внутри вложенных `Do` `Exit Do` циклов передает управление за пределы самого внутреннего цикла и в следующий более высокий уровень вложенности.  
  
## <a name="example"></a>Пример  
 В следующем примере операторы в цикле продолжают выполняться до тех пор, пока `index` переменная не будет больше 10. `Until` Предложение находится в конце цикла.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Пример  
 В следующем примере вместо `While` `Until` предложения используется предложение, которое проверяется в `condition` начале цикла, а не в конце.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Пример  
 В следующем примере останавливается цикл `condition` , `index` если переменная больше 100. Однако инструкция в цикле `Exit Do` приводит к остановке цикла, если переменная индекса больше 10. `If`  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Пример  
 В следующем примере считываются все строки в текстовом файле. Метод открывает файл и возвращает объект <xref:System.IO.StreamReader> , считывающий символы. <xref:System.IO.File.OpenText%2A> В условии <xref:System.IO.StreamReader.Peek%2A> метод`StreamReader` определяет наличие дополнительных символов. `Do...Loop`  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>См. также

- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
