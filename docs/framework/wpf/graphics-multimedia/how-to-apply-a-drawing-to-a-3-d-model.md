---
title: Практическое руководство. Применение рисования к трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459364"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Практическое руководство. Применение рисования к трехмерной модели

В этом примере показано, как использовать <xref:System.Windows.Media.DrawingBrush> в качестве <xref:System.Windows.Media.Media3D.Material>, применяемого к трехмерной модели.

Следующий код определяет <xref:System.Windows.Media.DrawingGroup> как содержимое <xref:System.Windows.Media.DrawingBrush>.  <xref:System.Windows.Media.DrawingBrush> задается как свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> <xref:System.Windows.Media.Media3D.DiffuseMaterial>, применяемое к трехмерной плоскости.

> [!NOTE]
> Часто желательно определить сложные объекты и значения, такие как рисунок ниже, как ресурсы, которые можно использовать повторно и упростить код. Дополнительные сведения см. в разделе [ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) .

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Пример

В следующем коде показан весь пример.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>См. также

- [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Создание трехмерной сцены](how-to-create-a-3-d-scene.md)
- [Обзор объектов Drawing](drawing-objects-overview.md)
- [Обзор трехмерной графики](3-d-graphics-overview.md)
