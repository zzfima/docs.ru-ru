---
title: "Практическое руководство. Отклонение элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9da10e4eb6cf045c6c4936b76f847f21ea1495e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-skew-an-element"></a>Практическое руководство. Отклонение элемента
В этом примере показано, как использовать <xref:System.Windows.Media.SkewTransform> для наклона элемента. Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат. Одним из примеров использования <xref:System.Windows.Media.SkewTransform> является имитация [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] глубина в [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] объектов.  
  
 Используйте <xref:System.Windows.Media.SkewTransform.CenterX%2A> и <xref:System.Windows.Media.SkewTransform.CenterY%2A> точка свойства для указания центра <xref:System.Windows.Media.SkewTransform>.  
  
 Используйте <xref:System.Windows.Media.SkewTransform.AngleX%2A> и <xref:System.Windows.Media.SkewTransform.AngleY%2A> свойства для указания угол отклонения оси x и оси y и наклонять текущей системы координат по осям эти.  
  
 Чтобы спрогнозировать результат наклона, примите во внимание <xref:System.Windows.Media.SkewTransform.AngleX%2A> наклон значений по оси x относительно исходной системы координат. Таким образом, для <xref:System.Windows.Media.SkewTransform.AngleX%2A> равно 30, ось y поворачивается на 30 градусов через начало координат и наклон значений в x-30 градусов от этого начала координат. Аналогичным образом <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 наклон значений y фигуры на 30 градусов от начала координат. Обратите внимание, что это не то же самое, что перенос (перемещение) системы координат на 30 градусов по осям X и Y.  
  
 В следующем примере применяется горизонтальный наклон в 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (0,0).  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 В следующем примере применяется горизонтальный наклон в 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (25,25).  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 В следующем примере применяется вертикальной искажение 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (25,25).  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 На следующем рисунке показаны отклонения, использованные в этом примере.  
  
 ![Примеры SkewTransform](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
Показаны три примера SkewTransform  
  
 Полный пример см. в разделе [Примеры двумерных преобразований](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
