---
title: "Практическое руководство. Удаление данных рукописного ввода в настраиваемом элементе управления | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "пользовательские элементы управления, стирание рукописного ввода"
  - "рукописный ввод, стирание на пользовательском элементе управления"
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Удаление данных рукописного ввода в настраиваемом элементе управления
Средство <xref:System.Windows.Ink.IncrementalStrokeHitTester> определяет, пересекается ли текущий росчерк с другим росчерком.  Эта функция полезна при создании элемента управления, позволяющего пользователю стирать части начертания на полотне <xref:System.Windows.Controls.InkCanvas> при установке режима <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> в значение <xref:System.Windows.Controls.InkCanvasEditingMode>.  
  
## Пример  
 В следующем примере создается настраиваемый элемент управления, позволяющий пользователю стирать части росчерков.  В этом примере создается элемент управления, содержащий данные рукописного ввода после инициализации.  Сведения о создании элемента управления, получающего данные рукописного ввода, см. в разделе [Создание элемента управления рукописным вводом](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]