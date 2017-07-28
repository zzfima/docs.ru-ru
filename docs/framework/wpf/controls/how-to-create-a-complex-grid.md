---
title: "Практическое руководство. Создание сложной сетки | Microsoft Docs"
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
  - "календарь, создание"
  - "Grid - элемент управления, создание, сложная сетка"
  - "помесячный календарь, создание"
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Создание сложной сетки
В этом примере показано использование <xref:System.Windows.Controls.Grid> для создания макета, который выглядит как календарь.  
  
## Пример  
 В следующем примере определяется восемь строк и восемь столбцов с помощью классов <xref:System.Windows.Controls.RowDefinition> и <xref:System.Windows.Controls.ColumnDefinition>.  В примере используются вложенные свойства <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=fullName> и <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=fullName>, а также элементы <xref:System.Windows.Shapes.Rectangle>, которые заполняют фон различных столбцов и строк.  Это построение возможно, так как принципиальное различие между <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Documents.Table> состоит в том, что в каждой ячейке <xref:System.Windows.Controls.Grid> может присутствовать несколько элементов.  
  
 В данном примере вертикальные градиенты используются для применения <xref:System.Windows.Shapes.Shape.Fill%2A> к столбцам и строкам, что позволяет улучшить визуальное представление и удобочитаемость календаря.  Стилизованные элементы <xref:System.Windows.Controls.TextBlock> представляют даты и дни недели.  Элементы <xref:System.Windows.Controls.TextBlock> расположены абсолютным образом в пределах своих ячеек с помощью свойства <xref:System.Windows.FrameworkElement.Margin%2A> и свойств выравнивания, которые определены внутри стиля приложения.  
  
 [!code-xml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## См. также  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Documents.TableCell>   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)