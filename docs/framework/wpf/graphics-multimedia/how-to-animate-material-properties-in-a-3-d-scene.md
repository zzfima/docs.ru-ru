---
title: "Практическое руководство. Анимация свойств материалов в трехмерной сцене | Microsoft Docs"
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
  - "трехмерные сцены, анимация свойств Material"
  - "анимация, свойства Material в трехмерных сценах"
  - "свойства Material, анимация в трехмерных сценах"
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Анимация свойств материалов в трехмерной сцене
В этом примере демонстрируется анимация свойства <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.Media3D.Material> применяемая к [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] модели.  
  
 В следующем примере кода определяется <xref:System.Windows.Media.LinearGradientBrush>, используемый как <xref:System.Windows.Media.Media3D.Material>, применяемый к 3\-D объекту.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 Свойство <xref:System.Windows.Media.Brush.Opacity%2A> этого <xref:System.Windows.Media.LinearGradientBrush> анимировано с помощью приведенного ниже примера кода.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## Пример  
 Следующий код показывает весь пример.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## См. также  
 [Создание трехмерной сцены](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)