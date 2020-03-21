---
title: 'Как: Применить рисунок к 3D-модели'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112184"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a>Как: Применить рисунок к 3D-модели

В этом примере <xref:System.Windows.Media.DrawingBrush> показано, <xref:System.Windows.Media.Media3D.Material> как использовать применяемый к 3D-модели.

Следующий код определяет <xref:System.Windows.Media.DrawingGroup> как содержимое <xref:System.Windows.Media.DrawingBrush>.  Устанавливается <xref:System.Windows.Media.DrawingBrush> как <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial> прикладного к 3D плоскости.

> [!NOTE]
> Часто желательно определить сложные объекты и значения, такие как приведенный ниже рисунок, как ресурсы, которые могут быть повторно использованы и упростить код. Дополнительную информацию можно узнать на [примере XAML Resources.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Пример

Следующий код показывает весь образец.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>См. также раздел

- [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Создание 3D-сцены](how-to-create-a-3-d-scene.md)
- [Общие сведения об объектах Drawing](drawing-objects-overview.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
