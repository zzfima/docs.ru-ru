---
title: Практическое руководство. Создание трехмерной сцены
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: e3c2ea803961ca57606f8ea8bec21d50a38dbe1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-3-d-scene"></a>Практическое руководство. Создание трехмерной сцены
В этом примере показано, как создать трехмерный объект, который выглядит как плоский листа бумаги, вращающийся. Объект <xref:System.Windows.Controls.Viewport3D> вместе со следующими компонентами используются для создания этой простой трехмерной сцены:  
  
-   Камера создается с помощью <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Камера определяет, какая часть трехмерной сцене для просмотра.  
  
-   Сетка создается для указания формы трехмерного объекта (лист бумаги) с помощью <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Материал указывается отображаемый на поверхности объекта (линейный градиент в этом образце) с помощью <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Светлый создается для освещения объекта с помощью <xref:System.Windows.Media.Media3D.DirectionalLight>.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано создание объемной сцены в XAML.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано создание той же объемной сцены в процедурном коде.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
