---
title: "Оператор GoTo | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GoTo"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ветвление"
  - "ветвление, conditional"
  - "ветвление, безусловный"
  - "условные операторы, GoTo - оператор"
  - "поток управления, ветвление"
  - "GoTo - оператор"
  - "GoTo - оператор, синтаксис"
  - "безусловное ветвление"
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Оператор GoTo
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Безусловно передает управление в указанную строку процедуры.  
  
## Синтаксис  
  
```  
GoTo line  
```  
  
## Часть  
 `line`  
 Обязательный.  Метка строки.  
  
## Заметки  
 Оператор `GoTo` может передавать управление только в строки процедуры, в которой он находится.  Строка должна иметь метку строки, на которую может сослаться `GoTo`.  Дополнительные сведения см. в разделе [Практическое руководство. Операторы меток](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
>  Операторы `GoTo` могут осложнить читаемость и отладку кода.  По возможности используйте управляющую структуру.  Дополнительные сведения см. в разделе [Управление ходом выполнения](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Нельзя использовать оператор `GoTo` для передачи управления из кода вне конструкции `For`...`Next`, `For Each`...`Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With` или `Using` ... `End Using` на метку внутри этой конструкции.  
  
## Конструкции Try и ветвления  
 В пределах конструкции `Try`...`Catch`...`Finally` применяются следующие правила для ветвления с помощью оператора `GoTo`.  
  
|Блок или область|Ветвление внутрь извне|Ветвление вовне|  
|----------------------|----------------------------|---------------------|  
|Блок `Try`|Только из блока `Catch` той же конструкции<sup>1</sup>|Только вовне всей конструкции|  
|Блок `Catch`|Никогда не разрешено|Только вовне всей конструкции или в блок `Try` той же конструкции<sup>1</sup>|  
|Блок `Finally`|Никогда не разрешено|Никогда не разрешено|  
  
 <sup>1</sup> Если одна конструкция `Try`... `Catch`... `Finally` вложена в другую, блок `Catch` может передавать управление в блок `Try` на своем уровне вложенности, но не в любой другой блок `Try`.  Вложенная конструкция `Try`... `Catch`... `Finally` должна полностью содержаться в блоке `Try` или `Catch` той конструкции, в которую вложена.  
  
 На следующем рисунке показана одна конструкция `Try`, вложенная в другую.  Различные ветви между блоками двух конструкций помечаются как допустимые или нет.  
  
 ![Графическая схема ветвления в конструкциях Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")  
Допустимые и недопустимые ветви в конструкциях Try  
  
## Пример  
 В следующем примере используется оператор `GoTo` для передачи управления на метки в процедуре.  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## См. также  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)   
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)