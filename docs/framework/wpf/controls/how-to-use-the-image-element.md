---
title: Практическое руководство. Использование элемента изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 164eee7c10d9e388c6e6ee695af479ca2d6974b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958328"
---
# <a name="how-to-use-the-image-element"></a>Практическое руководство. Использование элемента изображения
В этом примере показано, как включить изображения в приложение с помощью <xref:System.Windows.Controls.Image> элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как построить изображение шириной 200 пикселей. В этом примере [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения изображения используются как синтаксис атрибута, так и синтаксис тега свойства. Дополнительные сведения о синтаксисе атрибутов и синтаксисе свойств см. в разделе [Общие сведения о свойствах зависимостей](../advanced/dependency-properties-overview.md). Объект <xref:System.Windows.Media.Imaging.BitmapImage> используется для определения исходных данных изображения и явно определен для примера синтаксиса тега свойства. Кроме <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> того, <xref:System.Windows.Media.Imaging.BitmapImage> для свойства задается та же <xref:System.Windows.Controls.Image>ширина, что и <xref:System.Windows.FrameworkElement.Width%2A> в свойстве. Это позволяет использовать минимальный объем памяти при построении изображения.  
  
> [!NOTE]
> В общем случае, если необходимо указать размер отображаемого изображения, укажите только <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> или, но не оба. Если задано одно значение, пропорции изображения сохраняются. В противном случае изображение может внезапно оказаться растянутым или искривленным. Чтобы управлять поведением растяжения изображения, используйте <xref:System.Windows.Controls.Image.Stretch%2A> свойства и. <xref:System.Windows.Controls.Image.StretchDirection%2A>  
  
> [!NOTE]
> При <xref:System.Windows.FrameworkElement.Width%2A> указании размера изображения с помощью или <xref:System.Windows.FrameworkElement.Height%2A>необходимо также задать <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> один и <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> тот же размер.  
  
 <xref:System.Windows.Controls.Image.Stretch%2A> Свойство определяет способ растяжения источника изображения для заполнения элемента изображения. Дополнительные сведения см. в описании перечисления <xref:System.Windows.Media.Stretch>.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как построить изображение шириной 200 пикселей с использованием кода.  
  
> [!NOTE]
> Свойства <xref:System.Windows.Media.Imaging.BitmapImage> установки должны выполняться <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> в блоке и <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> .  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения об обработке изображений](../graphics-multimedia/imaging-overview.md)
