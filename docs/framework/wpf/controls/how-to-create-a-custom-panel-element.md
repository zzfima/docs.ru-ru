---
title: Практическое руководство. Создание пользовательского элемента Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799142"
---
# <a name="how-to-create-a-custom-panel-element"></a>Практическое руководство. Создание пользовательского элемента Panel
## <a name="example"></a>Пример  
 В этом примере показано, как переопределить поведение макета по умолчанию элемента <xref:System.Windows.Controls.Panel> и создать пользовательские элементы макета, которые являются производными от <xref:System.Windows.Controls.Panel>.  
  
 В примере определяется простой настраиваемый элемент <xref:System.Windows.Controls.Panel> с именем `PlotPanel`, который позиционирует дочерние элементы в соответствии с двумя жестко заданными координатами x и y. В этом примере для свойств `x` и `y` задано значение `50`; Таким образом, все дочерние элементы располагаются в этом расположении по осям x и y.  
  
 Для реализации пользовательских поведений <xref:System.Windows.Controls.Panel> в примере используются методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>. Каждый метод возвращает <xref:System.Windows.Size> данные, необходимые для позиционирования и отрисовки дочерних элементов.  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Panel>
- [Общие сведения о панелях](panels-overview.md)
