---
title: "Практическое руководство. Создание трехмерной сцены | Microsoft Docs"
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
  - "трехмерные сцены"
  - "создание, трехмерные сцены"
  - "сцены, трехмерный"
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Создание трехмерной сцены
В этом примере описано создание трехмерного объекта, который выглядит как вращающийся плоский лист бумаги.  <xref:System.Windows.Controls.Viewport3D> вместе со следующими компонентами используются для создания этой простой трехмерной сцены:  
  
-   Камера создается с помощью класса <xref:System.Windows.Media.Media3D.PerspectiveCamera>.  Камера определяет, какая часть трехмерной сцены видима.  
  
-   Сетка создается для указания формы трехмерного объекта \(лист бумаги\) с помощью свойства <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> класса <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Материал, который будет отображаться на поверхности объекта \(линейный градиент в этом примере\), определяется с помощью свойства <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> класса <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Источник света создается для освещения объекта с помощью класса <xref:System.Windows.Media.Media3D.DirectionalLight>.  
  
## Пример  
 В следующем примере кода показано создание объемной сцены в XAML.  
  
 [!code-xml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## Пример  
 В следующем примере кода показано создание той же объемной сцены в процедурном коде.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## См. также  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)