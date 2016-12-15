---
title: "Оператор Resume | Microsoft Docs"
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
  - "vb.Resume"
  - "vb.ResumeNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Error - оператор, и Resume - оператор"
  - "ошибки [Visual Basic], возобновление после"
  - "выполнение"
  - "выполнение, возобновление"
  - "Next - оператор, Возобновить"
  - "Resume Next - оператор"
  - "Resume - оператор"
  - "Resume - оператор, синтаксис"
  - "ошибки во время выполнения, возобновление после"
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор Resume
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Возобновляет выполнение по окончании процедуры обработки ошибки.  
  
 Рекомендуется ознакомиться с использовать структурную обработку исключений в коде если возможно, вместо использования и неструктурная обработка исключений `On Error` и  `Resume` выписки.  Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Синтаксис  
  
```  
Resume [ Next | line ]  
```  
  
## Части  
 `Resume`  
 Обязательный.  Если ошибка произошла в той же процедуре, в которой находится обработчик ошибок, то выполнение возобновляется с оператора, который вызвал ошибку.  Если ошибка возникла в вызываемой процедуре, то выполнение возобновляется с оператора, который последним вызвал процедуру, содержащую обработчик ошибок.  
  
 `Next`  
 Необязательный.  Если ошибка возникла в той же процедуре, в которой находится обработчик ошибок, то выполнение возобновляется с оператора, непосредственно следующего за оператором, вызвавшим ошибку.  Если ошибка возникла в вызываемой процедуре, то выполнение возобновляется с оператора, непосредственно следующего за оператором, который последним вызвал процедуру, содержащую обработчик ошибок \(или оператор `On Error Resume Next`\).  
  
 `line`  
 Необязательный.  Выполнение возобновляется со строки, указанной в аргументе `line`.  Аргумент `line` является меткой или номером строки, которая должна находиться в той же процедуре, что и обработчик ошибок.  
  
## Заметки  
  
> [!NOTE]
>  Рекомендуется использовать структурную обработку исключений в коде если возможно, вместо использования и неструктурная обработка исключений `On Error` и  `Resume` выписки.  Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Если оператор `Resume` используется в месте, отличном от подпрограммы обработки ошибок, возникает ошибка.  
  
 Оператор `Resume` нельзя использовать в процедуре, содержащей инструкцию `Try...Catch...Finally`.  
  
## Пример  
 В этом примере инструкция `Resume` используется для окончания обработки ошибки в процедуре и возобновления выполнения, начиная с вызвавшего ошибку оператора.  Ошибка номер 55 генерируется, чтобы проиллюстрировать использование оператора `Resume`.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Сборка:** библиотека времени выполнения Visual Basic \(в Microsoft.VisualBasic.dll\)  
  
## См. также  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Оператор Error](../../../visual-basic/language-reference/statements/error-statement.md)   
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)