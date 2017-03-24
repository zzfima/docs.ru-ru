---
title: "Оператор Call (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Call"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Call - оператор"
  - "процедуры, Call - оператор"
  - "процедуры, вызов"
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Оператор Call (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Передает управление в процедуру `Function`, `Sub` или процедуру библиотеки динамической компоновки \(DLL\).  
  
## Синтаксис  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## Части  
 `procedureName`  
 Обязательный.  Имя вызываемой процедуры.  
  
 `argumentList`  
 Необязательный.  Список переменных или выражений, передаваемых вызываемой процедуре.  Несколько аргументов разделяются запятыми.  При включении `argumentList` следует заключить его в скобки.  
  
## Заметки  
 Можно использовать ключевое слово `Call` при вызове процедуры.  Для большинства вызовов процедуры не требуется использовать ключевое слово this.  
  
 Обычно используется ключевое слово `Call` если выражение с именем не начинается с идентификатором.  Не рекомендуется использование ключевого слова `Call` для другого.  
  
 Если процедура возвращает значение, то оператор `Call` отбрасывает его.  
  
## Пример  
 Следующий код демонстрирует 2 примерам ключевого слова where `Call` необходимости для вызова процедуры.  В обоих примерах, выражение не начинается с идентификатором.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Лямбда\-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)