---
title: Практическое руководство. Применение рисования к трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855883"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Практическое руководство. Применение рисования к трехмерной модели

В этом примере показано, как использовать <xref:System.Windows.Media.DrawingBrush> объект в <xref:System.Windows.Media.Media3D.Material> качестве примененного к трехмерной модели.

Следующий код определяет в <xref:System.Windows.Media.DrawingGroup> качестве содержимого. <xref:System.Windows.Media.DrawingBrush>  Задается <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> как свойство объекта, <xref:System.Windows.Media.Media3D.DiffuseMaterial> применяемого к трехмерной плоскости. <xref:System.Windows.Media.DrawingBrush>

> [!NOTE]
> Часто желательно определить сложные объекты и значения, такие как рисунок ниже, как ресурсы, которые можно использовать повторно и упростить код. Дополнительные сведения см. в разделе [ресурсы XAML](../advanced/xaml-resources.md) .

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Пример

В следующем коде показан весь пример.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>См. также

- [Ресурсы XAML](../advanced/xaml-resources.md)
- [Создание трехмерной сцены](how-to-create-a-3-d-scene.md)
- [Обзор объектов Drawing](drawing-objects-overview.md)
- [Обзор трехмерной графики](3-d-graphics-overview.md)
