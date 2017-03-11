---
title: "Оператор While... End While (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.While"
  - "vb.While...EndWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "While - оператор"
  - "While - оператор, While...End While"
  - "While...End While - операторы"
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Оператор While... End While (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Выполняет блок операторов, пока заданное условие `True`.  
  
## Синтаксис  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`condition`|Обязательное.  Выражение `Boolean`.  Если `condition` равно `Nothing`, Visual Basic обрабатывает его как `False`.|  
|`statements`|Необязательный параметр.  Одна или несколько инструкций, следующих за `While`, которые выполняются каждый раз, когда `condition` равно `True`.|  
|`Continue While`|Необязательный параметр.  Элемент управления перенаправления к следующей итерации блока `While`.|  
|`Exit While`|Необязательный параметр.  Передача управления за пределы блока `While`.|  
|`End While`|Обязательное.  Завершает определение блока `While`.|  
  
## Заметки  
 Пока условие остается равным `True`, для повторения операторов неограниченное число раз используйте структуру `While...End While`.  Для большей гибкости с условием, с которым происходит проверка или результат, для которого вы его проверяете, предпочтительнее использовать [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).  Если вы хотите повторить инструкцию заданное количество раз, [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md) обычно является лучшим выбором.  
  
> [!NOTE]
>  Ключевое слово `While` также используется в [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Предложение Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md) и [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Если `condition` равно `True`, все `statements` работают до тех пор, пока не встретится оператор `End While`.  Элемент управления затем возвращения к выписке `While` и `condition` повторно проверено.  Если `condition` по\-прежнему равно `True`, процесс повторяется.  Если это `False` элементу управления пропуски в выписке, которая следует за выпиской `End While`.  
  
 Оператор `While` всегда проверяет условие, прежде чем она запускает цикл.  Выполнение цикла продолжается до тех пор, пока значение условия остается `True`.  Если `condition``False`, то при первом вводе цикл, оно не будет выполняться, даже один раз.  
  
 `condition` обычно является результатом сравнения 2 значений, но может быть любым выражением, результатом которого является [Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) значение \(`True` или `False`\).  Это выражение может включать значение другого типа данных, таких как числовой тип, который был преобразован в `Boolean`.  
  
 Циклы `While` могут вкладываться друг в друга.  Также можно вложить друг в друга различные виды управляющих структур.  Дополнительные сведения см. в разделе [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Оставьте пока  
 Оператор [Оставьте пока](../../../visual-basic/language-reference/statements/exit-statement.md) может предоставить другим способом оставить цикл `While`.  Элемент управления непосредственно к `Exit While` производит передачу выписке, которая следует за выпиской `End While`.  
  
 Обычно используется `Exit While` после некоторое условие оценивается \(например, в структуре `If...Then...Else` \).  Выход из цикла может потребоваться при обнаружении условия, которое делает бесполезным или невозможным продолжение итераций, например ошибочное значение или запрос на завершение.  Можно использовать `Exit While` при тестировании условие, которое может привести к *бесконечному циклу*, цикл, который может выполнять очень большой или даже на бесконечное число раз.  Затем можно использовать `Exit While` для выхода цикл.  
  
 Любое число операторов `Exit While` можно разместить в любом месте цикла `While`.  
  
 При использовании вложенных циклов `While` оператор `Exit While` передаст управление за пределы самого внутреннего цикла следующему уровню вложения.  
  
 `Continue While` выписки управление немедленно производит передачу к следующей итерации цикла.  Дополнительные сведения см. в разделе [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## Пример  
 В следующем примере инструкции в цикле выполняются до тех пор, пока значение переменной `index` остается больше 10.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_1.vb)]  
  
## Пример  
 В следующем примере показано использование оператора `Continue While` и `Exit While`.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_2.vb)]  
  
## Пример  
 В следующем примере выполняется чтение всех строк текстового файла.  Метод <xref:System.IO.File.OpenText%2A> открывает файл и возвращает <xref:System.IO.StreamReader>, который считывает символы.  В условии `While`, метод <xref:System.IO.StreamReader.Peek%2A>`StreamReader` определяет, содержит ли файл дополнительные символы.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_3.vb)]  
  
## См. также  
 [Циклические структуры](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Тип данных Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)