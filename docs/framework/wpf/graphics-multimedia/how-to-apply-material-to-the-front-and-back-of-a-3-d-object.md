---
title: "Практическое руководство. Применение материала к лицевой и обратной стороне трехмерного объекта"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce4605208be264418088399253298798205c3f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a>Практическое руководство. Применение материала к лицевой и обратной стороне трехмерного объекта
В следующем примере показано, как применить <xref:System.Windows.Media.Media3D.Material> к лицевой и обратной стороне трехмерного объекта и анимация объекта для отображения обеих сторон объекта. <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Свойство <xref:System.Windows.Media.Media3D.GeometryModel3D> используется для применения красной <xref:System.Windows.Media.Brush> в передней части объекта и <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D> используется для применения синий <xref:System.Windows.Media.Brush> к обратной стороне объекта. В следующем примере кода показано применение материалов к объекту:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Пример  
 Ниже приведен пример целиком.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Создание трехмерной сцены](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Анимация свойств материалов в трехмерной сцене](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [Применение эмиссионного материала к трехмерному объекту](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
