---
title: Практическое руководство. Привязка свойств двух элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "63809521"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Практическое руководство. Привязка свойств двух элементов управления
В этом примере показано, как привязать свойство одного экземпляра элемента управления к другому с помощью <xref:System.Windows.Data.Binding.ElementName%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как привязать <xref:System.Windows.Controls.Panel.Background%2A> свойство <xref:System.Windows.Controls.Canvas> для <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> Свойство <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 После преобразования пример выглядит следующим образом:  
  
![Снимок экрана: поле со списком установлен со значением зеленый и зеленый квадратик.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> Свойство цели привязки (в этом примере <xref:System.Windows.Controls.Panel.Background%2A> свойство) должно быть свойством зависимостей. Более подробную информацию см. в разделе [Общие сведения о связывании данных](data-binding-overview.md).  
  
## <a name="see-also"></a>См. также

- [Указание источника привязки](how-to-specify-the-binding-source.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
