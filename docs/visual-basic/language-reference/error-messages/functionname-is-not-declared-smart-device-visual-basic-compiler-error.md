---
title: "&lt;имяФункции&gt; не объявлена (Ошибка компилятора Smart Device/Visual Basic) | Microsoft Docs"
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
  - "bc30766"
  - "vbc30766"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30766"
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;имяФункции&gt; не объявлена (Ошибка компилятора Smart Device/Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<`functionname`\> не объявлен.  Функции ввода\-вывода файлов обычно доступны в пространстве имен `Microsoft.VisualBasic`, однако используемая версия .NET Compact Framework его не поддерживает.  
  
 **Идентификатор ошибки**: BC30766  
  
### Чтобы исправить эту ошибку  
  
-   Выполните операции с файлами с помощью функций, определенных в пространстве имен `System.IO`.  
  
## См. также  
 <xref:System.IO>   
 [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)