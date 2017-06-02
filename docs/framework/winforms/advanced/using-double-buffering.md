---
title: "Двойная буферизация графики | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "буферизация, двойная буферизация"
  - "двойная буферизация"
  - "мерцание, сокращение в Windows Forms"
  - "графика, двойная буферизация"
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Двойная буферизация графики
Двойная буферизация графики позволяет снизить эффект мерцания в приложениях, выполняющих сложные графические операции.  В .NET Framework имеется встроенная поддержка двойной буферизации, но можно также управлять визуализацией графики и вручную.  
  
## В этом подразделе  
 [Двойная буферизация графики](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Знакомство с принципами двойной буферизации и описание поддержки двойной буферизации в .NET Framework.  
  
 [Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Использование встроенной стандартной поддержки двойной буферизации в .NET Framework.  
  
 [Практическое руководство. Управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Управление двойной буферизацией в приложениях.  
  
 [Практическое руководство. Визуализация буферизированной графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Визуализация графики с двойной буферизацией.  
  
## Ссылка  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Методы элементов управления для работы двойной буферизацией.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Методы для создания графических буферов.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Доступ к контексту буферизованной графики для домена приложения.