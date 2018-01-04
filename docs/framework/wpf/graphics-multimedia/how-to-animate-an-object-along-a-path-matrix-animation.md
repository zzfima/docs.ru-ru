---
title: "Практическое руководство. Анимация объекта вдоль пути (матричная анимация)"
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
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb1bbe43c7e1797d5943bf3da6b4aca22a11c3a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>Практическое руководство. Анимация объекта вдоль пути (матричная анимация)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> класса для анимации объекта вдоль пути, который определяется <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Пример  
 Следующий пример анимирует объект вдоль пути следующим образом:  
  
-   Применяет <xref:System.Windows.Media.MatrixTransform> к объекту, чтобы переместить его.  
  
-   Определяет путь с помощью <xref:System.Windows.Media.PathGeometry>.  
  
-   Создает <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и использует его для анимации <xref:System.Windows.Media.Matrix> свойство <xref:System.Windows.Media.MatrixTransform>. <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Принимает <xref:System.Windows.Media.PathGeometry> и использует их для создания <xref:System.Windows.Media.Matrix> значения.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 Полный пример см. в разделе [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028). Дополнительные сведения о геометрических путях см. в разделе [конфигурациях](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Пример анимации вдоль пути](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Практические руководства, посвященные анимации по контуру](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
