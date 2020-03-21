---
title: 'Как: Оживлень Материальные Свойства в 3D-сцене'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112197"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>Как: Оживлень Материальные Свойства в 3D-сцене
В этом примере показано, <xref:System.Windows.Media.Brush.Opacity%2A> как <xref:System.Windows.Media.Media3D.Material> оживить свойство применяемого к 3D-модели.  
  
 Следующий пример кода <xref:System.Windows.Media.LinearGradientBrush> определяет используемый как применяемый <xref:System.Windows.Media.Media3D.Material> к 3D-объекту.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 Свойство <xref:System.Windows.Media.Brush.Opacity%2A> этого <xref:System.Windows.Media.LinearGradientBrush> анимировано с помощью приведенного ниже примера кода.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Пример  
 Следующий код показывает весь образец.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Создание 3D-сцены](how-to-create-a-3-d-scene.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
