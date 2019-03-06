---
title: Практическое руководство. Создание элемента сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: 5aa0e5b617d952fd5df1f80ae0ff146a6899aa32
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379514"
---
# <a name="how-to-create-a-grid-element"></a>Практическое руководство. Создание элемента сетки
## <a name="example"></a>Пример  
 В следующем примере показано, как создать и использовать экземпляр <xref:System.Windows.Controls.Grid> либо при помощи [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода. В этом примере используются три <xref:System.Windows.Controls.ColumnDefinition> объектов и три <xref:System.Windows.Controls.RowDefinition> объектов для создания сетки, который принимает девять ячеек, как в рабочем листе. Каждая ячейка содержит <xref:System.Windows.Controls.TextBlock> содержит элемент, который представляет данные, а верхняя строка <xref:System.Windows.Controls.TextBlock> с <xref:System.Windows.Controls.Grid.ColumnSpan%2A> свойства применен. Показать границы каждой ячейки, <xref:System.Windows.Controls.Grid.ShowGridLines%2A> включено свойство.  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  Любой из этих подходов создаст пользовательский интерфейс, который всегда выглядит практически так же, как показано ниже.

  ![Снимок экрана показан пользовательский интерфейс WPF, который содержит сетку разбить на три столбца.  Есть заголовок "2018 г. продукты поставляются» охват всех столбцов в верхней строке и содержит три столбца с показателями продаж для определенного квартала.  В нижней строке имеется текст, охватывающая два столбца с сообщением "Общее количество единиц: 300,000'](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Grid>
- [Общие сведения о панелях](panels-overview.md)
