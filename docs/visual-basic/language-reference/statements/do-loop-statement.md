---
title: "Оператор Do...Loop (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- "conditional statements [Visual Basic], Do�Loop"
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- "loop structures [Visual Basic], Do�Loop statements"
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 79d25dce963f383a84b56ce2c9b600fc2d5a7937
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="doloop-statement-visual-basic"></a>Оператор Do...Loop (Visual Basic)
Повторяет блок операторов, пока `Boolean` условие `True` или пока условия не станет `True`.  
  
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
|`Do`|Обязательный. Начинается определение `Do` цикла.|  
|`While`|Является обязательным, если используется параметр `Until`. Повторите цикл до `condition` — `False`.|  
|`Until`|Является обязательным, если используется параметр `While`. Повторите цикл до `condition` — `True`.|  
|`condition`|Необязательно. `Boolean`выражение. Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.|  
|`statements`|Необязательно. Один или несколько операторов, которые повторяются во время или до, `condition` — `True`.|  
|`Continue Do`|Необязательно. Передает управление следующей итерации цикла `Do` цикла.|  
|`Exit Do`|Необязательно. Передает управление из `Do` цикла.|  
|`Loop`|Обязательный. Завершает определение `Do` цикла.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `Do...Loop` структуры, если вы хотите повторить набор инструкций на неопределенное количество раз, пока условие выполняется. Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.  
  
 Можно использовать любой `While` или `Until` для указания `condition`, но не оба.  
  
 Можно проверить `condition` только один раз в начале или конце цикла. Если вы тестируете `condition` в начале цикла (в `Do` инструкции), цикл не может запускаться хотя бы один раз. Если вы тестируете в конце цикла (в `Loop` инструкции), цикл всегда выполняется по крайней мере один раз.  
  
 Условие обычно является результатом сравнения двух значений, но он может быть любое выражение, результатом которого является [тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`). Сюда входят значения других типов данных, таких как числовые типы, которые были преобразованы в `Boolean`.  
  
 Можно вложить `Do` циклы, поместив цикл один в другой. Также можно вложить различные виды управляющих структур друг с другом. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  `Do...Loop` Структура обеспечивает большую гибкость, чем [во время... Оператор End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , так как она позволяет решить, следует ли завершить цикл при `condition` перестает быть `True` или когда сначала становится `True`. Он также позволяет тестировать `condition` в начале или конце цикла.  
  
## <a name="exit-do"></a>Exit  
 [Выхода выполните](../../../visual-basic/language-reference/statements/exit-statement.md) инструкции можно предоставить альтернативный способ выйти из `Do…Loop`. `Exit Do`Управление передается оператору, следующему `Loop` инструкции.  
  
 `Exit Do`часто используется после оценки некоторого условия, например в `If...Then...Else` структуры. Может потребоваться выйти из цикла при обнаружении условия, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Один из способов использования `Exit Do` используется для проверки условия, которое может вызвать *бесконечный цикл*, который является цикл, который может запустить большое или возможно, бесконечное число раз. Можно использовать `Exit Do` для выхода из цикла.  
  
 Можно включить любое количество `Exit Do` инструкций в любом месте в `Do…Loop`.  
  
 При использовании внутри вложенной `Do` циклы, `Exit Do` передает управление из самого внутреннего цикла и отправляются верхнего уровня вложенности.  
  
## <a name="example"></a>Пример  
 В следующем примере инструкции в цикле по-прежнему выполняются, пока `index` переменной больше 10. `Until` Предложения — в конце цикла.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `While` предложение вместо `Until` предложения, и `condition` проверяется в начале цикла, а не в конце.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `condition` останавливающее цикл при `index` переменной больше 100. `If` Инструкции в цикле, однако вызывает `Exit Do` инструкции для остановки цикла, когда переменная индекса превышает 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 Следующий пример считывает все строки в текстовом файле. <xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы. В `Do...Loop` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, являются ли все дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
