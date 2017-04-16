---
title: "Практическое руководство. Создание элемента сетки | Microsoft Docs"
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
  - "Grid - элемент управления, создание, экземпляр сетки"
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Создание элемента сетки
## Пример  
 В следующем примере демонстрируется создание и использование экземпляра класса <xref:System.Windows.Controls.Grid> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода.  В этом примере для создания сетки из девяти ячеек \(как в рабочем листе\) используется три объекта <xref:System.Windows.Controls.ColumnDefinition> и три объекта <xref:System.Windows.Controls.RowDefinition>.  В каждой ячейке содержится элемент <xref:System.Windows.Controls.TextBlock>, представляющий данные. В верхней строке содержится объект <xref:System.Windows.Controls.TextBlock>, к которому применено свойство <xref:System.Windows.Controls.Grid.ColumnSpan%2A>.  Для отображения границ каждой ячейки включено свойство <xref:System.Windows.Controls.Grid.ShowGridLines%2A>.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## См. также  
 <xref:System.Windows.Controls.Grid>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)