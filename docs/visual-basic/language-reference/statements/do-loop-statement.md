---
title: "Оператор Do...Loop (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Do"
  - "vb.Loop"
  - "vb.Until"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "условные операторы, Do...Loop"
  - "Do - циклы"
  - "Do - оператор"
  - "Do...Loop - операторы"
  - "do-while - операторы"
  - "выполнение, условный"
  - "Exit - оператор, в операторы Do...Loop"
  - "инструкции, повтор"
  - "Loop - ключевое слово, Do...Loop - операторы"
  - "циклические структуры, Do…Loop - операторы"
  - "циклы, выход"
  - "Until - ключевое слово, Do...Loop - операторы"
  - "while - оператор, Do...Loop"
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
caps.latest.revision: 37
caps.handback.revision: 37
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Do...Loop (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Повторяет блок инструкций, пока условие `Boolean` равно `True` или до тех пор, пока условие станет `True`.  
  
## Синтаксис  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`Do`|Обязательное.  Начало определения цикла `Do`.|  
|`While`|Требуется, если используется `Until`.  Повторяет цикл до тех пор, пока `condition` равно `False`.|  
|`Until`|Требуется, если используется `While`.  Повторяет цикл до тех пор, пока `condition` равно `True`.|  
|`condition`|Необязательный параметр.  Выражение `Boolean`.  Если `condition` равно `Nothing`, Visual Basic обрабатывает его как `False`.|  
|`statements`|Необязательный параметр.  Один или несколько операторов, повторяемых, пока `condition` равно или пока не станет равно `True`.|  
|`Continue Do`|Необязательный параметр.  Элемент управления перенаправления к следующей итерации цикла `Do`.|  
|`Exit Do`|Необязательный параметр.  Передача управления из цикла `Do`.|  
|`Loop`|Обязательное.  Завершение определения цикла `Do`.|  
  
## Заметки  
 Используется структура `Do...Loop`, если требуется повторение набора инструкций неограниченное число раз, пока условие выполняется.  Если вы хотите повторить инструкцию определенное количество раз, то [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.  
  
 `While` или `Until` можно использовать для указания `condition`, но не оба одновременно.  
  
 Можно проверить `condition` только один раз — в начале или в конце цикла.  Если проверить `condition` в начале цикла \(в инструкции `Do`\), цикл может никогда не выполниться, даже один раз.  Если проверить в конце цикла \(в инструкции `Loop`\), цикл всегда выполняется по крайней мере один раз.  
  
 Условие обычно является результатом сравнения двух значений, но оно может быть любым выражением, значение которого при вычислении имеет тип [Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) \(`True` или `False`\).  Сюда же относятся значения других типов данных, например, числовых типов, преобразованные в тип `Boolean`.  
  
 Циклы `Do` могут вкладываться друг в друга.  Также можно вложить друг в друга различные виды управляющих структур.  Дополнительные сведения см. в разделе [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  Структура `Do...Loop` имеет большую гибкость, чем [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md), поскольку она позволяет выбрать, следует ли завершать цикл, когда `condition` перестанет быть равным `True`, либо в случае, когда станет равно `True`.  Это также позволяет проверить `condition` в начале либо в конце цикла.  
  
## Exit Do  
 Оператор [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) дает альтернативный способ выхода из `Do…Loop`.  `Exit Do` немедленно передает управление оператору, следующему за оператором `Loop`.  
  
 `Exit Do` часто используется после оценки некоторого условия, например в структуре `If...Then...Else`.  Выход из цикла может потребоваться при обнаружении условия, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение.  `Exit Do`, в частности, применяется для тестирования условия, которое может вызвать *бесконечный цикл*, т. е. цикл, повторяемый много раз или бесконечно.  `Exit Do` можно использовать для выхода из цикла.  
  
 Любое число операторов `Exit Do` можно разместить в любом месте `Do…Loop`.  
  
 При использовании вложенных циклов `Do` оператор `Exit Do` передаст управление за пределы самого внутреннего цикла следующему уровню вложения.  
  
## Пример  
 В следующем примере инструкции в цикле выполняются до тех пор, пока значение переменной `index` остается больше 10.  Предложение`Until` завершает цикл.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## Пример  
 В следующем примере используется оператор `While`  вместо `Until` , и `condition` проверяется в начале цикла, а не в конце.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## Пример  
 В следующем примере условие `condition` останавливает цикл, когда переменная `index`  больше 100.  Оператор `If` в цикле, однако, вызывает инструкцию `Exit Do` , чтобы остановить цикл, когда переменная index больше 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## Пример  
 В следующем примере выполняется чтение всех строк текстового файла.  Метод <xref:System.IO.File.OpenText%2A> открывает файл и возвращает <xref:System.IO.StreamReader>, который считывает символы.  В условии `Do...Loop` метод <xref:System.IO.StreamReader.Peek%2A> `StreamReader` определяет, есть ли какие\-либо дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## См. также  
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)