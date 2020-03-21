---
title: Как анимировать 3D переводы
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112262"
---
# <a name="how-to-animate-3d-translations"></a>Как анимировать 3D переводы
Эта тема демонстрирует, как оживить преобразование перевода, установленное на 3D-модели.  
  
 Приведенный ниже код показывает <xref:System.Windows.Media.Media3D.TranslateTransform3D> применение <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> объекта к <xref:System.Windows.Media.Media3D.GeometryModel3D>свойству .  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 Свойство <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> этого <xref:System.Windows.Media.Media3D.TranslateTransform3D> объекта анимировано с помощью приведенного ниже кода.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Пример  
 Следующий код показывает весь образец.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Создание 3D-сцены](how-to-create-a-3-d-scene.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
- [Общие сведения о классах Transform](transforms-overview.md)
