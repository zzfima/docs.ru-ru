---
title: "Оператор REM (Visual Basic) | Microsoft Docs"
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
  - "vb.'"
  - "vb.Rem"
  - "Rem"
  - "'"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "' - знак комментария [Visual Basic]"
  - "комментарии к коду, Visual Basic"
  - "комментарии, код Visual Basic"
  - "REM - оператор"
  - "код Visual Basic, комментарии"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор REM (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используется для включения пояснительных примечаний в исходный код программы.  
  
## Синтаксис  
  
```  
REM comment  
' comment  
```  
  
## Части  
 `comment`  
 Необязательный.  Текст включаемого примечания.  Необходим пробел между `REM` ключевое слово и `comment`.  
  
## Заметки  
 Оператор `REM` можно поместить в отдельной строке или в строке за другим оператором.  Оператор `REM` должен быть последним оператором в строке.  Если примечание следует после другого оператора, зарезервированное слово `REM` должно отделяться от этого оператора пробелом.  
  
 Вместо `REM` можно использовать одинарные кавычки \(`'`\).  Это правило действует и для примечания, следующего за другим оператором в той строке, и для примечания, занимающего всю строку.  
  
> [!NOTE]
>  Продолжить инструкцию `REM` с помощью последовательности символов, используемой обычно для переноса строки \(`_`\), невозможно.  После того как компилятор встречает признак начала комментария, анализ смысла дальнейших знаков прерывается.  Для создания многострочных примечаний необходимо вставлять в каждую строку примечания оператор `REM` или символ примечания \(`'`\).  
  
## Пример  
 В данном примере показано использование оператора `REM` для вставки в программу пояснительных примечаний.  Также демонстрируется использование вместо `REM` символа одиночной кавычки \(`'`\).  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## См. также  
 [Комментарии в коде](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)   
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)