---
title: "Как Использовать класс FontSizeConverter | Microsoft Docs"
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
  - "объекты FontSizeConverter"
  - "оформление, объекты FontSizeConverter"
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Как Использовать класс FontSizeConverter
## Пример  
 Этот пример демонстрирует создание экземпляра <xref:System.Windows.FontSizeConverter> и использование его для изменения размера шрифта.  
  
 Пример определяет пользовательский метод с именем `changeSize`, который преобразует содержимое <xref:System.Windows.Controls.ListBoxItem>, как определенное в отдельном файле [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], к экземпляру <xref:System.Double> и позже к <xref:System.String>.  Этот метод передает <xref:System.Windows.Controls.ListBoxItem> объекту <xref:System.Windows.FontSizeConverter>, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> в экземпляр <xref:System.Double>.  Это значение затем передается обратно в качестве значения свойства <xref:System.Windows.Controls.TextBlock.FontSize%2A> <xref:System.Windows.Controls.TextBlock>.  
  
 Этот пример также определяет второй пользовательский метод с именем `changeFamily`.  Этот метод преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> в <xref:System.String>, и затем передает это значение свойства <xref:System.Windows.Controls.TextBlock.FontFamily%2A> элемента <xref:System.Windows.Controls.TextBlock>.  
  
 Этот пример не запускается.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## См. также  
 <xref:System.Windows.FontSizeConverter>