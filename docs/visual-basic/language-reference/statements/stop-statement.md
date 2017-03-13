---
title: "Оператор Stop (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Stop"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "точки останова, Stop - операторы"
  - "выполнение, остановка"
  - "выполнение, приостановка"
  - "процессы, прерывание"
  - "обработка, прерывание"
  - "Stop - операторы"
  - "Stop - операторы, синтаксис"
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Оператор Stop (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Приостанавливает выполнение.  
  
## Синтаксис  
  
```  
Stop  
```  
  
## Заметки  
 Можно помещать операторы `Stop` в любом месте процедуры для приостановки выполнения.  Использование оператора `Stop` аналогично установке точки останова в коде.  
  
 Оператор `Stop` приостанавливает выполнение, однако, в отличие от `End`, не закрывает файлы и не очищает переменные, если только не встречается в скомпилированном исполняемом файле \(с расширением EXE\).  
  
> [!NOTE]
>  Если оператор `Stop` находится в коде, запущенном вне интегрированной среды разработки \(IDE\), то запускается отладчик.  Это происходит вне зависимости от того, скомпилирован ли код в отладочном или в рабочем режиме.  
  
## Пример  
 В данном примере оператор `Stop` используется для приостановки выполнения на каждом шаге цикла `For...Next`.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## См. также  
 [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md)