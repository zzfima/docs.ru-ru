---
title: "Практическое руководство. Использование свойства BetweenShowDelay | Microsoft Docs"
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
  - "BetweenShowDelay - свойство времени"
  - "ToolTip - элемент управления, BetweenShowDelay - свойство времени"
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Использование свойства BetweenShowDelay
В данном примере демонстрируется использование свойства времени <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> таким образом, что подсказки отображаются быстро — с минимальными задержками или без них — при перемещении пользователем указателя мыши с одной подсказки непосредственно на другую.  
  
## Пример  
 В следующем примере значение свойства <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> равно одной секунде \(1000 миллисекунд\), а значение свойства <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> равно двум секундам \(2000 мс\) для подсказок обоих элементов управления <xref:System.Windows.Shapes.Ellipse>.  Если отображается подсказка одного из эллипсов и указатель мыши перемещается на другой эллипс в течение двух секунд и останавливается на нем, то подсказка второго эллипса отображается немедленно.  
  
 В любом из следующих скриптов применяется свойство <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, в результате чего подсказка для второго эллипса появится с задержкой в одну секунду:  
  
-   Если время, затрачиваемое на перемещение на вторую кнопку, будет составлять более двух секунд.  
  
-   Если подсказка не отображается в начале временного интервала для первого эллипса.  
  
 [!code-xml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## См. также  
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Практические руководства](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)   
 [Общие сведения о всплывающих подсказках](../../../../docs/framework/wpf/controls/tooltip-overview.md)