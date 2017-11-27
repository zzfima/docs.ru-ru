---
title: "Практическое руководство. Поворот объекта с использованием геометрического пути (матрица анимации)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c624b221c1e4c122728887a9d592a3275d8f8e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Практическое руководство. Поворот объекта с использованием геометрического пути (матрица анимации)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и <xref:System.Windows.Media.MatrixTransform> для поворота (вращения) объекта вдоль геометрического пути, определенного <xref:System.Windows.Media.PathGeometry> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> анимируемый объект <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform>. <xref:System.Windows.Media.MatrixTransform> Применяется к кнопке и приводит к перемещению в пути кривой. Поскольку <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойству `true`, прямоугольник поворачивается вдоль касательной к пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Полный пример см. в разделе [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 В версии кода в предыдущем примере используется <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.EllipseGeometry>, несмотря на то, что была применена только одна анимация. Более простой способ применения одиночной анимации к свойству в коде является использование <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода. Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Практические руководства, посвященные анимации по контуру](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Пример анимации вдоль пути](http://go.microsoft.com/fwlink/?LinkID=160028)
