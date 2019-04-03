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
ms.openlocfilehash: 3ff3d67f38f510b798da3e470de066cff1e98f29
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826045"
---
# <a name="doloop-statement-visual-basic"></a>Оператор Do...Loop (Visual Basic)
Повторяет блок операторов, пока `Boolean` условие `True` или пока условие не станет `True`.  
  
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
|`While`|Является обязательным, если используется параметр `Until`. Повторите цикл до `condition` является `False`.|  
|`Until`|Является обязательным, если используется параметр `While`. Повторите цикл до `condition` является `True`.|  
|`condition`|Необязательный параметр. `Boolean` выражение. Если `condition` — `Nothing`, Visual Basic рассматривает его как `False`.|  
|`statements`|Необязательный параметр. Один или несколько операторов, которые повторяются во время или до, `condition` является `True`.|  
|`Continue Do`|Необязательный параметр. Передает управление следующей итерации `Do` цикла.|  
|`Exit Do`|Необязательный параметр. Передает управление из `Do` цикла.|  
|`Loop`|Обязательный. Завершает определение `Do` цикла.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `Do...Loop` структуры повторения набор инструкций неограниченное число раз, пока условие выполняется. Если вы хотите повторить инструкцию set несколько раз, [для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.  
  
 Можно использовать либо `While` или `Until` для указания `condition`, но не оба.  
  
 Вы можете протестировать `condition` только один раз, в начале или конце цикла. Если вы проверяете `condition` в начале цикла (в `Do` инструкции), цикл не может запустить еще один раз. Если вы тестируете в конце цикла (в `Loop` инструкции), цикл всегда выполняется по крайней мере один раз.  
  
 Условие обычно является результатом сравнения двух значений, но он может быть любое выражение, результатом которого является [логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение (`True` или `False`). Сюда входят значения других типов данных, например числовых типов, которые были преобразованы в `Boolean`.  
  
 Можно вложить `Do` циклы, поместив в одном цикле в другую. Можно также вложить разные виды структур управления друг с другом. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  `Do...Loop` Структура дает большую гибкость, чем [хотя... Оператор End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) так, как это дает возможность решить, следует ли завершить цикл при `condition` перестает быть `True` или когда сначала становится `True`. Он также позволяет тестировать `condition` в начале или конце цикла.  
  
## <a name="exit-do"></a>Exit  
 [Выйти из сделать](../../../visual-basic/language-reference/statements/exit-statement.md) оператор может предоставить альтернативный способ выхода из `Do…Loop`. `Exit Do` Управление передается оператору, который расположен `Loop` инструкции.  
  
 `Exit Do` часто используется после вычисления некоторого условия, например в `If...Then...Else` структуры. Может потребоваться выйти из цикла, если определяет условие, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение. Один из способов использования `Exit Do` — проверить условие, которое может привести к *бесконечный цикл*, который является цикл, который может запустить большое или возможно, бесконечное число раз. Можно использовать `Exit Do` для выхода из цикла.  
  
 Можно включить любое число `Exit Do` инструкций в любом месте в `Do…Loop`.  
  
 При использовании внутри вложенной `Do` циклы, `Exit Do` передает управление из самого внутреннего цикла и поместить в следующий уровень вложенности.  
  
## <a name="example"></a>Пример  
 В следующем примере операторы в цикле продолжать выполняться до `index` переменной превышает 10. `Until` Предложение находится в конце цикла.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `While` предложение вместо `Until` предложение, и `condition` тестируется в начале цикла, а не в конце.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Пример  
 В следующем примере `condition` останавливающее цикл при `index` переменной превышает 100. `If` Оператора цикла, однако вызывает `Exit Do` инструкции для остановки цикла, когда переменная индекса превышает 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Пример  
 В следующем примере считываются все строки в текстовом файле. <xref:System.IO.File.OpenText%2A> Метод открывает файл и возвращает <xref:System.IO.StreamReader> , считывает символы. В `Do...Loop` условие, <xref:System.IO.StreamReader.Peek%2A> метод `StreamReader` определяет, существуют ли все дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>См. также

- [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Логический тип данных](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
