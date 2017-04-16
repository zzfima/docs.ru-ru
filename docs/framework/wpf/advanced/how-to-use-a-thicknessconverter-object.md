---
title: "Практическое руководство. Использование объекта ThicknessConverter | Microsoft Docs"
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
  - "граница - толщина"
  - "объекты ThicknessConverter"
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Использование объекта ThicknessConverter
## Пример  
 В этом примере демонстрируется создание экземпляра <xref:System.Windows.ThicknessConverter> и его использование для изменения толщины границы.  
  
 В примере задается пользовательский метод с именем `changeThickness`; сначала этот метод преобразует содержимое <xref:System.Windows.Controls.ListBoxItem>, как определено в отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файле, в экземпляр <xref:System.Windows.Thickness>, а затем преобразует это содержимое в <xref:System.String>.  Этот метод передает <xref:System.Windows.Controls.ListBoxItem> объекту <xref:System.Windows.ThicknessConverter>, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> в экземпляр <xref:System.Windows.Thickness>.  Это значение затем передается обратно в качестве значения свойства <xref:System.Windows.Controls.Border.BorderThickness%2A> элемента <xref:System.Windows.Controls.Border>.  
  
 Этот пример не запускается.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## См. также  
 <xref:System.Windows.Thickness>   
 <xref:System.Windows.ThicknessConverter>   
 <xref:System.Windows.Controls.Border>   
 [How to: Change the Margin Property](http://msdn.microsoft.com/ru-ru/8a313efd-5f99-4097-b4c1-8fa49d8379a2)   
 [How to: Convert a ListBoxItem to a new Data Type](http://msdn.microsoft.com/ru-ru/7a080b88-184e-4b27-bb61-d42bafba9727)   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)