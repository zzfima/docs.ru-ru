---
title: "Оператор Exit (Visual Basic) | Microsoft Docs"
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
  - "vb.Exit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "код, выход"
  - "выполнение, завершение"
  - "выполнение, остановка"
  - "Exit - оператор"
  - "файлы, закрытие"
  - "завершение программы"
  - "программы, выход"
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Exit (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Завершает процедуру или блок и передает управление оператору, следующему непосредственно после вызова процедуры или определения блока.  
  
## Синтаксис  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## Операторы  
 `Exit Do`  
 Немедленный выход из цикла `Do`, в котором находится этот элемент.  Выполнение продолжается с инструкции, следующей за инструкцией `Loop`.  `Exit Do` можно использовать только внутри цикла `Do`.  При использовании вложенных циклов `Do` оператор `Exit Do` закрывает самый внутренний цикл и передает управление следующему уровню вложения.  
  
 `Exit For`  
 Немедленный выход из цикла `For`, в котором находится этот элемент.  Выполнение продолжается с инструкции, следующей за инструкцией `Next`.  `Exit For` можно использовать только внутри цикла `For`...`Next` или `For Each`...`Next`.  При использовании вложенных циклов `For` оператор `Exit For` закрывает самый внутренний цикл и передает управление следующему уровню вложения.  
  
 `Exit Function`  
 Немедленный выход из процедуры `Function`, в которой находится этот элемент.  Выполнение продолжается с инструкции, следующей за инструкцией, вызвавшей процедуру `Function`.  `Exit Function` можно использовать только внутри процедуры `Function`.  
  
 Чтобы задать возвращаемое значение, можно присвоить значение имени функции в строке перед оператором `Exit Function`.  Для присвоения возвращаемого значения и завершения функции в одном операторе можно воспользоваться [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Exit Property`  
 Немедленный выход из процедуры `Property`, в которой находится этот элемент.  Выполнение продолжается с инструкции, которая вызвала процедуру `Property`, т. е. с инструкции, запрашивающей или задающей значение свойства.  `Exit Property` можно использовать только внутри процедуры `Get` или `Set` свойства.  
  
 Чтобы задать возвращаемое значение в процедуре `Get`, можно присвоить значение имени функции в линии до оператора `Exit Property`.  Для присвоения возвращаемого значения и завершения процедуры `Get` в одном операторе можно воспользоваться оператором `Return`.  
  
 В процедуре `Set` оператор `Exit Property` эквивалентен оператору `Return`.  
  
 `Exit Select`  
 Немедленный выход из блока `Select Case`, в котором находится этот элемент.  Выполнение продолжается с инструкции, следующей за инструкцией `End Select`.  `Exit Select` можно использовать только внутри инструкции `Select Case`.  
  
 `Exit Sub`  
 Немедленный выход из процедуры `Sub`, в которой находится этот элемент.  Выполнение продолжается с инструкции, следующей за инструкцией, вызвавшей процедуру `Sub`.  `Exit Sub` можно использовать только внутри процедуры `Sub`.  
  
 В процедуре `Sub` оператор `Exit Sub` эквивалентен оператору `Return`.  
  
 `Exit Try`  
 Немедленный выход из блока `Try` или `Catch`, в котором находится этот элемент.  Выполнение продолжается с блока `Finally`, если он имеется; в противном случае — с инструкции, следующей за инструкцией `End Try`.  `Exit Try` можно использовать только внутри блока `Try` или `Catch`, но не внутри блока `Finally`.  
  
 `Exit While`  
 Немедленный выход из цикла `While`, в котором находится этот элемент.  Выполнение продолжается с инструкции, следующей за инструкцией `End While`.  `Exit While` можно использовать только внутри цикла `While`.  При использовании во вложенных циклах `While`, оператор `Exit While` передает управление циклу, находящемуся на один уровень выше цикла, в котором находится `Exit While`.  
  
## Заметки  
 Не следует путать инструкции `Exit` и `End`.  `Exit` не определяет конец инструкции.  
  
## Пример  
 В следующем примере условие цикла останавливает цикл, когда переменная `index` больше 100.  Оператор `If` в цикле, однако, вызывает инструкцию `Exit Do` , чтобы остановить цикл, когда переменная index больше 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## Пример  
 В следующем примере возвращаемое значение присваивается имени функции `myFunction` и затем используется оператор `Exit Function` для возврата из функции.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## Пример  
 В следующем примере используется [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md), чтобы назначить возвращаемое значение и выйти из функции.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## См. также  
 [Оператор Continue](../../../visual-basic/language-reference/statements/continue-statement.md)   
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)   
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Return](../../../visual-basic/language-reference/statements/return-statement.md)   
 [Оператор Stop](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)