---
title: Практическое руководство. Получение или задание свойств размещения Canvas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 294b49d427a67da849ce930cf29a48f1735bf135
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Практическое руководство. Получение или задание свойств размещения Canvas
В этом примере показано, как использовать методы размещения элемента <xref:System.Windows.Controls.Canvas> для размещения содержимого дочернего элемента. В этом примере используется содержимое в <xref:System.Windows.Controls.ListBoxItem> для представления значений размещения и преобразования их в экземпляры <xref:System.Double>, который является обязательным аргументом для позиционирования. Затем значения преобразуются обратно в строки и отображаются в виде текста <xref:System.Windows.Controls.TextBlock> элемента с помощью <xref:System.Windows.Controls.Canvas.GetLeft%2A> метод.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Windows.Controls.ListBox> элемент, который имеет одиннадцать выбираемых <xref:System.Windows.Controls.ListBoxItem> элементов. <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Триггеров событий `ChangeLeft` пользовательский метод, который определяет последующего блока кода.  
  
 Каждый <xref:System.Windows.Controls.ListBoxItem> представляет <xref:System.Double> значение, которое является одним из аргументов, <xref:System.Windows.Controls.Canvas.SetLeft%2A> метод <xref:System.Windows.Controls.Canvas> принимает. Чтобы использовать <xref:System.Windows.Controls.ListBoxItem> для представления экземпляра <xref:System.Double>, необходимо сначала преобразовать <xref:System.Windows.Controls.ListBoxItem> правильный тип данных.  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Когда пользователь изменяет <xref:System.Windows.Controls.ListBox> выбора, он вызывает `ChangeLeft` пользовательский метод. Этот метод передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.LengthConverter> объекта, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру <xref:System.Double> (Обратите внимание, что это значение уже был преобразован в <xref:System.String> с помощью <xref:System.Windows.Controls.Control.ToString%2A> метод). Это значение затем передается обратно <xref:System.Windows.Controls.Canvas.SetLeft%2A> и <xref:System.Windows.Controls.Canvas.GetLeft%2A> методы <xref:System.Windows.Controls.Canvas> Чтобы изменить положение `text1` объекта.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
