---
title: "Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic) | Microsoft Docs"
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
  - "bc30830"
  - "vbc30830"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30830"
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Операторы Line больше не поддерживаются  Функциональные возможности файлового ввода\-вывода доступны как `Microsoft.VisualBasic.FileSystem.LineInput` и графические возможности доступны как `System.Drawing.Graphics.DrawLine`.  
  
 **Идентификатор ошибки:** BC30830  
  
### Чтобы исправить эту ошибку  
  
1.  Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Если осуществляется вывод графики, используйте `System.Drawing.Graphics.Drawline`.  
  
## См. также  
 <xref:System.IO>   
 <xref:System.Drawing>   
 [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)