---
title: "Практическое руководство. Переопределение метода панели OnRender | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "overriding OnRender method"
  - "Panel control, overriding OnRender method"
  - "OnRender method"
  - "controls, Panel, overriding OnRender method"
helpviewer_keywords: 
  - "OnRender - метод, переопределение"
  - "переопределение метода OnRender элемента управления Panel"
  - "Panel - элемент управления, переопределение метода OnRender"
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Переопределение метода панели OnRender
В данном примере показано переопределение метода <xref:System.Windows.Controls.Panel.OnRender%2A> элемента <xref:System.Windows.Controls.Panel> для добавления пользовательских графических эффектов в элемент макета.  
  
## Пример  
 Для добавления графических эффектов в отображаемый элемент панели используется метод <xref:System.Windows.Controls.Panel.OnRender%2A>.  Например, этот метод можно использовать для добавления пользовательских эффектов границы или фона.  Объект <xref:System.Windows.Media.DrawingContext> передается в качестве аргумента, предоставляющего методы для отображения фигур, текста, изображений или видео.  Этот метод полезен для настройки объекта панели.  
  
 [!code-csharp[LightWeightCustomPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## См. также  
 <xref:System.Windows.Controls.Panel>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Custom Radial Panel Sample](http://go.microsoft.com/fwlink/?LinkID=159982)   
 [Практические руководства](../../../../docs/framework/wpf/controls/panel-how-to-topics.md)