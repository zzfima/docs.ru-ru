---
title: Как привязать свойства двух элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: d38c473b8c4d3f71f1e3decd4f66be248665c57b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974817"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Как привязать свойства двух элементов управления

В этом примере показано, как привязать свойство одного экземпляра элемента управления к другому с помощью свойства <xref:System.Windows.Data.Binding.ElementName%2A>.

## <a name="example"></a>Пример

В следующем примере показано, как привязать свойство <xref:System.Windows.Controls.Panel.Background%2A> <xref:System.Windows.Controls.Canvas> к свойству [SelectedItem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) <xref:System.Windows.Controls.ComboBox>:

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

После преобразования пример выглядит следующим образом:

![Снимок экрана, показывающий поле со списком со значением зеленого цвета и зеленым квадратом.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> Свойство цели привязки (в этом примере свойство <xref:System.Windows.Controls.Panel.Background%2A>) должно быть свойством зависимостей. Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../../desktop-wpf/data/data-binding-overview.md).

## <a name="see-also"></a>См. также

- [Указание источника привязки](how-to-specify-the-binding-source.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
