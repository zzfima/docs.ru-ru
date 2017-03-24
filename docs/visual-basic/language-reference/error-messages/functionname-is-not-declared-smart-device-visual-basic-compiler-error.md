---
title: "&lt;имяФункции&gt; не объявлена (Ошибка компилятора Smart Device/Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30766"
  - "vbc30766"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30766"
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# &lt;имяФункции&gt; не объявлена (Ошибка компилятора Smart Device/Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

\<`functionname`\> не объявлен.  Функции ввода\-вывода файлов обычно доступны в пространстве имен `Microsoft.VisualBasic`, однако используемая версия .NET Compact Framework его не поддерживает.  
  
 **Идентификатор ошибки**: BC30766  
  
### Чтобы исправить эту ошибку  
  
-   Выполните операции с файлами с помощью функций, определенных в пространстве имен `System.IO`.  
  
## См. также  
 <xref:System.IO>   
 [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)