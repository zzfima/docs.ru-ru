---
title: "Практическое руководство. Управление часами в интерактивном режиме | Microsoft Docs"
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
  - "часы, интерактивное управление"
  - "интерактивное управление часами"
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Управление часами в интерактивном режиме
Свойство <xref:System.Windows.Media.Animation.ClockController> объекта <xref:System.Windows.Media.Animation.Clock> позволяет в интерактивном режиме запускать, приостанавливать, возобновлять, обращаться, перемещать значение по периоду и останавливать часы.  Только корневые часы временного дерева поддерживают управление в интерактивном режиме.  
  
> [!NOTE]
>  Существуют другие способы интерактивного управления анимированием, не требующие непосредственной работы с часами, например, раскадровки.  Раскадровки поддерживаются в разметке и коде.  Примеры см. в разделе [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) или [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 В следующем примере несколько кнопок используется для управления анимированными часами в интерактивном режиме.  
  
## Пример  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## См. также  
 [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)