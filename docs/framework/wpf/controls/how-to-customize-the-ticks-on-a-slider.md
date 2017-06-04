---
title: "Практическое руководство. Настройка делений на ползунке | Microsoft Docs"
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
  - "TickBar"
  - "Ползунок, создание с помощью TickBar"
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Настройка делений на ползунке
В этом примере показано, как создать <xref:System.Windows.Controls.Slider> элемента управления, содержащего деления.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Controls.Primitives.TickBar> отображается при установке <xref:System.Windows.Controls.Slider.TickPlacement%2A> свойству значение, отличное от <xref:System.Windows.Controls.Primitives.TickPlacement>, которое является значением по умолчанию.  
  
 Следующий пример демонстрирует создание <xref:System.Windows.Controls.Slider> с <xref:System.Windows.Controls.Primitives.TickBar> отображает метки деления. <xref:System.Windows.Controls.Slider.TickPlacement%2A> и <xref:System.Windows.Controls.Slider.TickFrequency%2A> определяют расположение меток делений и интервал между ними. При перемещении <xref:System.Windows.Controls.Primitives.Thumb>, всплывающие подсказки отображают значение <xref:System.Windows.Controls.Slider>. <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> свойство определяет, где появляется подсказка. <xref:System.Windows.Controls.Primitives.Thumb> соответствуют движения расположение делений, так как <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> равен `true`.  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.Slider.Ticks%2A> свойства для создания деления отметок вдоль <xref:System.Windows.Controls.Slider> через нерегулярные интервалы времени.  
  
 [!code-xml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Slider>   
 <xref:System.Windows.Controls.Primitives.TickBar>   
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>   
 [Разделы руководства, посвященные ползунка](http://msdn.microsoft.com/ru-ru/534be86c-afb2-425d-8186-631278a9925e)