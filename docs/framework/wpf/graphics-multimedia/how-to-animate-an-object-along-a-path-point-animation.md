---
title: "Практическое руководство. Анимация объекта вдоль пути (точечная анимация) | Microsoft Docs"
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
  - "анимация, объекты вдоль путей (точечная анимация)"
  - "точечная анимация"
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Анимация объекта вдоль пути (точечная анимация)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimationUsingPath> анимируемого объекта <xref:System.Windows.Point> вдоль изогнутого пути.  
  
## <a name="example"></a>Пример  
 В следующем примере перемещается <xref:System.Windows.Media.EllipseGeometry> вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>. Эллипс <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойства, которое принимает <xref:System.Windows.Point> значением, определяет его положение; Чтобы переместить эллипс, можно анимировать его <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство. В примере используется <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации <xref:System.Windows.Media.EllipseGeometry> объекта <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.  
  
 [!code-xml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Полный пример см. [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 В версии кода в предыдущем примере используется <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.EllipseGeometry>, даже если была применена только одна анимация. Объект <xref:System.Windows.Media.Animation.Storyboard> часто является самым простым способом применения нескольких эффектов анимации, поскольку эти анимации можно управлять одним и тем же <xref:System.Windows.Media.Animation.Storyboard>. Однако, более простой способ применить одну анимацию к свойству при использовании кода является использование <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод. Например, в разделе [анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>См. также  
 [Пример анимации пути перемещения](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Разделы руководства, посвященные анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)