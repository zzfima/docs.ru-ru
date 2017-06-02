---
title: "Практическое руководство. Использование элемента изображения | Microsoft Docs"
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
  - "BitmapImage - класс"
  - "классы, BitmapImage"
  - "элементы управления, Изображение"
  - "элемент управления Image"
  - "отрисовка изображений"
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Использование элемента изображения
В данном примере показывается способ включения изображений в приложение с помощью элемента <xref:System.Windows.Controls.Image>.  
  
## Пример  
 В следующем примере показано, как отобразить изображение шириной 200 пикселей.  В этом примере [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для задания изображения используется синтаксис атрибута и синтаксис тега свойства.  Дополнительные сведения о синтаксисе атрибута и синтаксисе свойства см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  <xref:System.Windows.Media.Imaging.BitmapImage> используется для определения источника данных изображения и явно задается для примера синтаксиса тега свойства.  Кроме того, для <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> <xref:System.Windows.Media.Imaging.BitmapImage> устанавливается такая же ширина, как и для <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.Image>.  Это сделано для минимизации объема памяти при отрисовке изображения.  
  
> [!NOTE]
>  Как правило, если требуется указать размер визуализируемого изображения, устанавливается только <xref:System.Windows.FrameworkElement.Width%2A> или <xref:System.Windows.FrameworkElement.Height%2A>, но не оба сразу.  Если задано одно свойство, то [пропорции](GTMT) изображения сохраняются.  В противном случае изображение может оказаться растянутым или перекошенным.  Для управления растяжением изображения используются свойства <xref:System.Windows.Controls.Image.Stretch%2A> и <xref:System.Windows.Controls.Image.StretchDirection%2A>.  
  
> [!NOTE]
>  При указании размера изображения с помощью <xref:System.Windows.FrameworkElement.Width%2A> или <xref:System.Windows.FrameworkElement.Height%2A> следует также задать для <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>, либо <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> тот же соответствующий размер.  
  
 Свойство <xref:System.Windows.Controls.Image.Stretch%2A> определяет, как изображение источника имиджа растягивается для заполнения элемента изображения.  Дополнительные сведения см. в разделе <xref:System.Windows.Media.Stretch>.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## Пример  
 В следующем примере показано, как отобразить изображение шириной 200 пикселей с помощью кода.  
  
> [!NOTE]
>  Установка свойств <xref:System.Windows.Media.Imaging.BitmapImage> должна быть выполнена внутри блока <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> и <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A>.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)