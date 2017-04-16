---
title: "Практическое руководство. Создание и использование объекта GridLengthConverter | Microsoft Docs"
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
  - "Grid - элемент управления, создание, объекты GridLengthConverter"
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Создание и использование объекта GridLengthConverter
## Пример  
 В следующем примере показан процесс создания экземпляра <xref:System.Windows.GridLengthConverter>.  В примере определяется пользовательский метод с именем `changeCol`, который передает <xref:System.Windows.Controls.ListBoxItem> в <xref:System.Windows.GridLengthConverter>, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> в экземпляр <xref:System.Windows.GridLength>.  Затем преобразованное значение передается обратно в качестве значения свойства <xref:System.Windows.Controls.ColumnDefinition.Width%2A> элемента <xref:System.Windows.Controls.ColumnDefinition>.  
  
 В примере также определяется второй пользовательский метод с именем `changeColVal`.  Этот пользовательский метод преобразует <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> <xref:System.Windows.Controls.Slider> в <xref:System.String> и затем передает значение обратно в <xref:System.Windows.Controls.ColumnDefinition> в качестве <xref:System.Windows.Controls.ColumnDefinition.Width%2A> элемента.  
  
 Обратите внимание, что отдельный файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] определяет содержимое <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## См. также  
 <xref:System.Windows.GridLengthConverter>   
 <xref:System.Windows.GridLength>