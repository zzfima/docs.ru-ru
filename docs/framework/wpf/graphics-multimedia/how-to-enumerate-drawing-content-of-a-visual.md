---
title: Практическое руководство. Перечисление содержимого изображения визуального элемента
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930068"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Практическое руководство. Перечисление содержимого изображения визуального элемента
Объект предоставляет объектную модель для перечисления содержимого <xref:System.Windows.Media.Visual>. <xref:System.Windows.Media.Drawing>  
  
## <a name="example"></a>Пример  
 В следующем примере метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> используется для извлечения значения <xref:System.Windows.Media.DrawingGroup> из <xref:System.Windows.Media.Visual> и перечисления содержимого группы.  
  
> [!NOTE]
> При перечислении содержимого визуального элемента извлекаются объекты <xref:System.Windows.Media.Drawing>, а не базовое представление данных отрисовки в виде списка инструкций векторной графики. Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Обзор объектов Drawing](drawing-objects-overview.md)
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
