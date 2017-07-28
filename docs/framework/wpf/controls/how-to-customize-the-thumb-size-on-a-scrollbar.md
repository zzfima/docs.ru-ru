---
title: "Практическое руководство. Настройка размера ползунка в ScrollBar | Microsoft Docs"
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
  - "эскиз - подстройка размера"
  - "ScrollBar - элемент управления"
  - "размер эскиза"
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Настройка размера ползунка в ScrollBar
В этом разделе объясняется, как установить фиксированный размер <xref:System.Windows.Controls.Primitives.Thumb> элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar> и как задать минимальный размер <xref:System.Windows.Controls.Primitives.Thumb> элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## Пример  
  
## Описание  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> фиксированного размера.  В примере устанавливается свойство <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> элемента управления <xref:System.Windows.Controls.Primitives.Thumb> в значение <xref:System.Double.NaN> и высота <xref:System.Windows.Controls.Primitives.Thumb>.  Для создания горизонтального <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb>, который имеет фиксированную ширину, задайте ширину <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## Код  
 [!code-xml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## Описание  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> минимального размера.  В примере устанавливается значение свойства <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.  Для создания горизонтального <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb>, имеющим минимальную ширину, установите <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## Код  
 [!code-xml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## См. также  
 [Стили и шаблоны элемента ScrollBar](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)