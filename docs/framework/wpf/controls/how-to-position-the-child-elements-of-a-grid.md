---
title: Практическое руководство. Размещение дочерних элементов Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186723"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Практическое руководство. Размещение дочерних элементов Grid
В этом примере показано, как использовать методы <xref:System.Windows.Controls.Grid> получения и набора, которые определяются для размещения элементов ребенка.  
  
## <a name="example"></a>Пример  
 Следующий пример определяет <xref:System.Windows.Controls.Grid> родительский`grid1`элемент (), который имеет три столбца и три строки. Элемент <xref:System.Windows.Shapes.Rectangle> ребенка`rect1`() добавляется к нулю <xref:System.Windows.Controls.Grid> положения столбца, положение строки ноль. <xref:System.Windows.Controls.Button>элементы представляют методы, которые можно <xref:System.Windows.Shapes.Rectangle> назвать <xref:System.Windows.Controls.Grid>для переориентации элемента в пределах . Когда пользователь нажимает кнопку, соответствующий метод активируется.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 Следующий пример кода за рулем обрабатывает <xref:System.Windows.Controls.Primitives.ButtonBase.Click> методы, которые поднимают события кнопки. Пример записывает вызовы <xref:System.Windows.Controls.TextBlock> этих методов к элементам, которые используют связанные методы получения для вывода новых значений свойств в виде строк.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Вот законченный результат!

 ![скриншот изображает пользовательский интерфейс WPF с двумя столбцами, правая сторона имеет сетку 3 x 3, а левая имеет кнопки для перемещения цветного прямоугольника между столбцами и рядами сетки](././media/grid-methods-sample.png)
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Grid>
- [Общие сведения о панелях](panels-overview.md)
