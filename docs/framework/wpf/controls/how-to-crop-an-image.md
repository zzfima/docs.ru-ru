---
title: Практическое руководство. Обрезка изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 46c559356447688e52508b823cc260c13128208f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-crop-an-image"></a>Практическое руководство. Обрезка изображения
В этом примере показано, как обрезать изображение с помощью <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> в основном используется при кодировании обрезанной версии изображения для сохранения файла. Чтобы обрезать изображение, отображаемое в целях см. в разделе [Создание области отсечения](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) раздела.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] определяет ресурсы, используемые в примере, показанном ниже.  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 В следующем примере создается образ с помощью <xref:System.Windows.Media.Imaging.CroppedBitmap> в качестве источника.  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> Также может использоваться как источник другого <xref:System.Windows.Media.Imaging.CroppedBitmap>, цепочки обрезки. Обратите внимание, что <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> использует значения, которые относятся к источник обрезку растрового изображения и не начальный образ.  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>См. также  
 [Создание области отсечения](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
