---
title: "Практическое руководство. Создание расширителя с элементом ScrollViewer | Microsoft Docs"
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
  - "элементы управления [WPF], Expander"
  - "элементы управления [WPF], ScrollViewer"
  - "Expander - элемент управления, создание"
  - "ScrollViewer - элемент управления, с элементом управления Expander"
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Создание расширителя с элементом ScrollViewer
В этом примере демонстрируется создание элемента управления <xref:System.Windows.Controls.Expander>, который включает в себя сложное содержимое, такое как изображение и текст.  Пример также помещает содержимое <xref:System.Windows.Controls.Expander> в элемент управления <xref:System.Windows.Controls.ScrollViewer>.  
  
## Пример  
 В следующем примере показан способ создания объекта <xref:System.Windows.Controls.Expander>.  Пример использует элемент управления <xref:System.Windows.Controls.Primitives.BulletDecorator>, который содержит изображение и текст, для того чтобы определить <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.  Элемент управления <xref:System.Windows.Controls.ScrollViewer> предоставляет метод прокрутки для просмотра развернутого содержимого.  
  
 Обратите внимание, что в примере задается свойство <xref:System.Windows.FrameworkElement.Height%2A> в <xref:System.Windows.Controls.ScrollViewer> вместо содержимого.  Если <xref:System.Windows.FrameworkElement.Height%2A> установлен в содержимом, <xref:System.Windows.Controls.ScrollViewer> не позволяет пользователю прокручивать содержимое.  Свойство <xref:System.Windows.FrameworkElement.Width%2A> устанавливается в элементе управления <xref:System.Windows.Controls.Expander> и этот параметр применяется к <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и развернутому содержимому.  
  
 [!code-xml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## См. также  
 <xref:System.Windows.Controls.Expander>   
 [Общие сведения об элементе управления Expander](../../../../docs/framework/wpf/controls/expander-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)