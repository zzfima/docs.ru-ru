---
title: Как привязать свойства двух элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459179"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Как привязать свойства двух элементов управления
В этом примере показано, как привязать свойство одного экземпляра элемента управления к другому с помощью свойства <xref:System.Windows.Data.Binding.ElementName%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как привязать свойство <xref:System.Windows.Controls.Panel.Background%2A> <xref:System.Windows.Controls.Canvas> к <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> свойства <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 После преобразования пример выглядит следующим образом:  
  
![Снимок экрана, показывающий поле со списком со значением зеленого цвета и зеленым квадратом.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> Свойство цели привязки (в этом примере свойство <xref:System.Windows.Controls.Panel.Background%2A>) должно быть свойством зависимостей. Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>См. также

- [Указание источника привязки](how-to-specify-the-binding-source.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
