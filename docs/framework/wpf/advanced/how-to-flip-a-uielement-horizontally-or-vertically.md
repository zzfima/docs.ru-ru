---
title: "Как отразить объект UIElement по горизонтали или по вертикали | Microsoft Docs"
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
  - "отражение UIElements"
  - "UIElements, отражение"
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Как отразить объект UIElement по горизонтали или по вертикали
В этом примере показано, как использовать <xref:System.Windows.Media.ScaleTransform> для отражения объекта <xref:System.Windows.UIElement>.  В этом примере элемент управления <xref:System.Windows.Controls.Button> \(тип <xref:System.Windows.UIElement>\) зеркально отражен посредством применения объекта <xref:System.Windows.Media.ScaleTransform> к его свойству <xref:System.Windows.UIElement.RenderTransform%2A>.  
  
## Пример  
 На следующем рисунке показана кнопка для отражения.  
  
 ![Кнопка без преобразования](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.png "graphicsmm\_buttonflipbeforeflip")  
UIElement для отражения  
  
 Ниже приведен код, который создает кнопку.  
  
 [!code-xml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## Пример  
 Чтобы отразить кнопку горизонтально, создайте объект <xref:System.Windows.Media.ScaleTransform> и установите для его свойства <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> значение \-1.  Примените объект <xref:System.Windows.Media.ScaleTransform> к свойству <xref:System.Windows.UIElement.RenderTransform%2A> кнопки.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Кнопка, перевернута горизонтально &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.png "graphicsmm\_buttonfliphorizontalflip\_displaced")  
Кнопка после применения объекта ScaleTransform  
  
## Пример  
 Как видно из предыдущего рисунка, кнопка зеркально отражена, но также была перемещена.  Причина в том, что кнопка была отражена от верхнего левого угла.  Чтобы отразить кнопку на месте, нужно применить <xref:System.Windows.Media.ScaleTransform> к ее центру, а не к ее углу.  Простой способ применить <xref:System.Windows.Media.ScaleTransform> к центру кнопки — задать свойству кнопки <xref:System.Windows.UIElement.RenderTransformOrigin%2A> значение 0,5, 0,5.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Кнопка, перевернута горизонтально по центру](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.png "graphicsmm\_buttonfliphorizontalflip\_inplace")  
Кнопка со значением RenderTransformOrigin 0,5, 0,5  
  
## Пример  
 Чтобы отразить кнопку по вертикали, задайте свойство <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> объекта <xref:System.Windows.Media.ScaleTransform> вместо его свойства <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>.  
  
 [!code-xml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Кнопка, перевернута вертикально по центру](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.png "graphicsmm\_buttonflipverticalflip\_inplace")  
Вертикально отраженная кнопка  
  
## См. также  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)