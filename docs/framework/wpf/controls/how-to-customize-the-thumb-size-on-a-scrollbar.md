---
title: Практическое руководство. Настройка размера ползунка в ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 30fc72e3f0631b01777bf058c7a7470cc376a547
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354327"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>Практическое руководство. Настройка размера ползунка в ScrollBar
В этом разделе описывается настройка <xref:System.Windows.Controls.Primitives.Thumb> из <xref:System.Windows.Controls.Primitives.ScrollBar> фиксированный размер и как задать минимальный размер <xref:System.Windows.Controls.Primitives.Thumb> из <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## <a name="example"></a>Пример  
  
## <a name="description"></a>Описание  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> с фиксированным размером. В примере задается <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> свойство <xref:System.Windows.Controls.Primitives.Thumb> для <xref:System.Double.NaN> и задает высоту <xref:System.Windows.Controls.Primitives.Thumb>.  Чтобы создать горизонтальный <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> , которые имеют фиксированную ширину, задайте ширину <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## <a name="code"></a>Код  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>Описание  
 В следующем примере создается <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> с минимальным размером. В примере задается значение <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>. Чтобы создать горизонтальный <xref:System.Windows.Controls.Primitives.ScrollBar> с <xref:System.Windows.Controls.Primitives.Thumb> Минимальная ширина, задайте <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## <a name="code"></a>Код  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>См. также
- [Стили и шаблоны элемента ScrollBar](scrollbar-styles-and-templates.md)
