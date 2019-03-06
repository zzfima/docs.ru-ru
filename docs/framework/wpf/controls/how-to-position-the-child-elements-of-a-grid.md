---
title: Практическое руководство. Размещение дочерних элементов сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 90115bc6192a33f4c27eaa75ebfe6a7c9d1458e5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369179"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Практическое руководство. Размещение дочерних элементов сетки
В этом примере показано, как использовать команду get и задайте методы, определенные на <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется родительским <xref:System.Windows.Controls.Grid> элемент (`grid1`) с тремя столбцами и тремя строками. Дочерний элемент <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) добавляется к <xref:System.Windows.Controls.Grid> в столбец номер 0, строку номер 0. <xref:System.Windows.Controls.Button> элементы представляют собой методы, которые могут быть вызваны для изменения положения <xref:System.Windows.Shapes.Rectangle> сервисном <xref:System.Windows.Controls.Grid>. Когда пользователь нажимает кнопку, активируется связанный метод.  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 В следующем примере кода программной части обрабатывает методы, кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызывают события. Пример записывает эти вызовы методов в <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы получения для вывода новых значений свойств в виде строк.  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 Ниже приведен результат!
 
 ![Снимок экрана показан пользовательский интерфейс WPF с двумя столбцами, справа от оператора имеет 3 x 3 сетку и слева находятся кнопки для перемещения между столбцами и строками сетки цветным прямоугольником](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Grid>
- [Общие сведения о панелях](panels-overview.md)
