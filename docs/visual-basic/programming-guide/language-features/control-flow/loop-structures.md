---
title: "Циклические структуры (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "условные операторы, циклические структуры"
  - "поток управления, циклы"
  - "Do - оператор, Do - циклы"
  - "For - ключевое слово [Visual Basic], циклические структуры"
  - "циклические структуры"
  - "циклы"
  - "операторы [Visual Basic], цикл"
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Циклические структуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Циклические структуры в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] позволяют выполнить одну или несколько строк кода несколько раз.  Операторы в циклической структуре можно повторять следующим образом: пока условие не станет равно `True`, пока условие не станет равно `False`, указанное число раз или один раз для каждого элемента в коллекции.  
  
 На следующей иллюстрации показана структура цикла, выполняющего набор инструкций до тех пор, пока условие не станет истиной.  
  
 ![Таблица потока цикла “Do...Until”](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")  
Выполнение набора инструкций до тех пор, пока условие не станет истиной  
  
## Циклы While  
 Конструкция `While`...`End While` выполняет набор инструкций, пока значение условия, указанного в операторе `While`, равно `True`.  Дополнительные сведения см. в разделе [Оператор While...End While](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
## Циклы Do  
 Конструкция `Do`...`Loop` позволяет проверить условие в начале или в конце структуры цикла.  Можно также указать, следует ли повторять цикл, пока значение условия равно `True` или же до тех пор, пока оно не станет равно `True`.  Дополнительные сведения см. в разделе [Оператор Do...Loop](../../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Циклы For  
 Конструкция `For`...`Next` выполняет определенное число итераций.  Для отслеживания числа повторений в ней используется управляющая переменная цикла, называющаяся *счетчиком*.  Необходимо указать начальное и конечное значения для этого счетчика и при необходимости указать шаг, на который счетчик будет увеличен за одно повторение.  Дополнительные сведения см. в разделе [Оператор For...Next](../../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
## Циклы For Each  
 Конструкция `For Each`...`Next` выполняет набор инструкций один раз применительно к каждому элементу коллекции.  При этом указывается управляющая переменная цикла, но нет необходимости определения ее начального или конечного значения.  Дополнительные сведения см. в разделе [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## См. также  
 [Управление ходом выполнения](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)