---
title: "Практическое руководство. Как сделать UIElement прозрачным или полупрозрачным | Microsoft Docs"
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
  - "непрозрачность, элементов UIElement"
  - "прозрачность элементов UIElement"
  - "UIElements, непрозрачность"
  - "UIElements, прозрачность"
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Как сделать UIElement прозрачным или полупрозрачным
В этом примере демонстрируется, как сделать <xref:System.Windows.UIElement> прозрачным или полупрозрачным.  Чтобы сделать элемент прозрачным или полупрозрачным, следует присвоить значение свойству <xref:System.Windows.UIElement.Opacity%2A>.  Значение `0.0` делает элемент полностью прозрачным, а значение `1.0` делает элемент полностью непрозрачным.  Значение `0.5` делает элемент прозрачным на 50% и т. д.  По умолчанию свойству <xref:System.Windows.UIElement.Opacity%2A> элемента присваивается значение `1.0`.  
  
## Пример  
 В следующем примере свойству <xref:System.Windows.UIElement.Opacity%2A> кнопки присваивается значение `0.25`, что делает ее и ее содержимое \(в данном случае текст кнопки\) на 25% непрозрачной.  
  
 [!code-xml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Если содержимое элемента имеет собственные параметры <xref:System.Windows.UIElement.Opacity%2A>, то эти значения умножаются для содержащих элементов <xref:System.Windows.UIElement.Opacity%2A>.  
  
 В следующем примере свойство <xref:System.Windows.UIElement.Opacity%2A> кнопки имеет значение `0.25`, а свойство <xref:System.Windows.UIElement.Opacity%2A> элемента <xref:System.Windows.Controls.Image>, содержащегося в кнопке, равно `0.5`.  В результате изображение отображается на 12,5% непрозрачным: 0,25 \* 0,5 \= 0,125.  
  
 [!code-xml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Другой способ управления прозрачностью элемента заключается в установке прозрачности кисти <xref:System.Windows.Media.Brush>, которая рисует элемент.  Такой подход позволяет выборочно изменить непрозрачность частей элемента и предоставляет большую производительность, чем свойство элемента <xref:System.Windows.UIElement.Opacity%2A>.  В следующем примере свойству <xref:System.Windows.Media.Brush.Opacity%2A> кисти <xref:System.Windows.Media.SolidColorBrush>, которая используется для рисования фона <xref:System.Windows.Controls.Control.Background%2A> кнопки, присваивается значение `0.25`.  В результате фон кисти является на 25% непрозрачным, но его содержимое \(текст кнопки\) остаются на 100% непрозрачным.  
  
 [!code-xml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 Можно также управлять прозрачностью отдельных цветов в кисти.  Дополнительные сведения о цветах и кистях см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Пример, в котором показана анимация непрозрачности элемента, см. в разделе [Анимация прозрачности элемента или кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).