---
title: "Оператор Return (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Return"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "поток управления, возврат управления выражениям"
  - "выражения [Visual Basic], возврат управления"
  - "Return - оператор"
  - "Return - оператор, синтаксис"
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Оператор Return (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Возвращает управление коду, вызвавшему процедуру `Function`, `Sub` `Get`, `Set` или `Operator`.  
  
## Синтаксис  
  
```  
Return  
-or-  
Return expression  
```  
  
## Часть  
 `expression`  
 Является обязательным в процедурах `Function`, `Get` и `Operator`.  Выражение, представляющее значение, возвращаемое вызывающему коду.  
  
## Заметки  
 В процедуре `Sub` или `Set` оператор `Return` эквивалентен оператору `Exit Sub` или `Exit Property`, а `expression` не указывается.  
  
 В процедуре `Function`, `Get` или `Operator` оператор `Return` должен включать `expression`, а `expression` должно определяться значением типа данных, преобразуемого в возвращаемый тип процедуры.  В процедурах `Function` и `Get` имеется альтернативный способ назначения выражения имени процедуры для использования в качестве возвращаемого значения, а также выполнения операторов `Exit Function` и `Exit Property`.  В процедуре `Operator` следует использовать `Return` `expression`.  
  
 Можно включить столько операторов `Return`, сколько необходимо в той же процедуре.  
  
> [!NOTE]
>  Код в блоке `Finally` выполняется после того, как встретится оператор `Return` в блоке `Try` или `Catch` блок, но перед этим выполняется оператор `Return`.  A `Return` не удалось включить в выписку  `Finally` блок.  
  
## Пример  
 В следующем примере оператор `Return` используется несколько раз для возвращения из процедуры, если дальнейшие вычисления не нужны.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)