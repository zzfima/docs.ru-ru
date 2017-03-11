---
title: "Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30830"
  - "vbc30830"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30830"
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Операторы Line больше не поддерживаются  Функциональные возможности файлового ввода\-вывода доступны как `Microsoft.VisualBasic.FileSystem.LineInput` и графические возможности доступны как `System.Drawing.Graphics.DrawLine`.  
  
 **Идентификатор ошибки:** BC30830  
  
### Чтобы исправить эту ошибку  
  
1.  Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Если осуществляется вывод графики, используйте `System.Drawing.Graphics.Drawline`.  
  
## См. также  
 <xref:System.IO>   
 <xref:System.Drawing>   
 [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)