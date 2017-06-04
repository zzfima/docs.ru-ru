---
title: "Практическое руководство. Установка часов в синхронном режиме | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "часы, поиск в синхронном режиме"
  - "поиск по часам в синхронном режиме"
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Установка часов в синхронном режиме
Используйте метод <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> для синхронной установки часов в определенное значение.  В данном примере демонстрируются методы <xref:System.Windows.Media.Animation.ClockController.Seek%2A> и <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> класса <xref:System.Windows.Media.Animation.ClockController>.  
  
 В этом примере показано, как выполнить установку <xref:System.Windows.Media.Animation.Clock>; пример, демонстрирующий установку раскадровки, см. в разделе [Поиск раскадровки в синхронном режиме](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md).  
  
## Пример  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]