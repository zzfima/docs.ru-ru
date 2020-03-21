---
title: 'Как: Преобразовать масштаб 3D-модели'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111989"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>Как: Преобразовать масштаб 3D-модели
В этом примере показано, как масштабировать 3D-объект. Для масштабирования 3D-объекта <xref:System.Windows.Media.Media3D.ScaleTransform3D>используйте. В <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> и свойства изменить размер элемента фактор, который вы указываете. Например, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> значение 1,5 растягивает объект до 150 процентов от его первоначальной ширины. Значение <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 0,5 сжимает высоту объекта на 50 процентов. Приведенный ниже код <xref:System.Windows.Media.Media3D.ScaleTransform3D> показывает использование <xref:System.Windows.Media.Media3D.GeometryModel3D>преобразования для .  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Пример  
 Следующий код показывает весь образец.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Анимированные 3D переводы](how-to-animate-3-d-translations.md)
- [Создание 3D-сцены](how-to-create-a-3-d-scene.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
