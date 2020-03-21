---
title: 'Как: Создать 3D-сцену'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112106"
---
# <a name="how-to-create-a-3d-scene"></a>Как: Создать 3D-сцену
В этом примере показано, как создать 3D-объект, похожий на плоский лист бумаги, который был повернут. А <xref:System.Windows.Controls.Viewport3D> вместе со следующими компонентами используются для создания этой простой 3D сцены:  
  
- Камера создается с <xref:System.Windows.Media.Media3D.PerspectiveCamera>помощью . Камера определяет, какая часть 3D-сцены видна для просмотра.  
  
- Создается сетка для определения формы 3D-объекта (листа <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> бумаги) с использованием свойства <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
- Материал указан для отображения на поверхности объекта (линейный градиент в данном образце) с использованием <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> свойства <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
- Свет создается, чтобы сиять <xref:System.Windows.Media.Media3D.DirectionalLight>на объекте с помощью.  
  
## <a name="example"></a>Пример  
 В приведенном ниже коде показано, как создать 3D-сцену в XAML.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Пример  
 В приведенном ниже коде показано, как создать ту же 3D-сцену в процедурном коде.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [3D Графика Обзор](3-d-graphics-overview.md)
