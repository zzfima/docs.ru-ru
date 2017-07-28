---
title: "Практическое руководство. Преобразование масштаба трехмерной модели | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "трехмерные объекты, масштабирование"
  - "масштабирование, трехмерные объекты"
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Практическое руководство. Преобразование масштаба трехмерной модели
В этом примере демонстрируется масштабирование 3D объекта.  Для масштабирования 3D объекта используйте <xref:System.Windows.Media.Media3D.ScaleTransform3D>.  Свойства <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> и <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> изменяют размер элемента в зависимости от указанного коэффициента.  Например, при значении <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, равном 1,5, объект увеличивается на 150 процентов от его исходной ширины.  При значение 0,5 для <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> элемент сжимается по высоте на 50 процентов.  В следующем примере кода демонстрирует использование <xref:System.Windows.Media.Media3D.ScaleTransform3D> в качестве преобразования для <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## Пример  
 Следующий код показывает весь пример.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## См. также  
 [Анимация трехмерных преобразований](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)   
 [Создание трехмерной сцены](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)