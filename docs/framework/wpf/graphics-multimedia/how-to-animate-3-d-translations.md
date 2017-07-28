---
title: "Практическое руководство. Анимация трехмерных преобразований | Microsoft Docs"
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
  - "трехмерные преобразования, анимирование"
  - "анимация, трехмерные преобразования"
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Анимация трехмерных преобразований
В этом разделе демонстрируется анимация преобразования перевода в [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]\-модели.  
  
 В программном коде, приведенном ниже, показано применение объекта <xref:System.Windows.Media.Media3D.TranslateTransform3D> к свойству <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> модели <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 Свойство <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> объекта <xref:System.Windows.Media.Media3D.TranslateTransform3D> анимировано с помощью приведенного ниже кода.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## Пример  
 Следующий код показывает весь пример.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Создание трехмерной сцены](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)