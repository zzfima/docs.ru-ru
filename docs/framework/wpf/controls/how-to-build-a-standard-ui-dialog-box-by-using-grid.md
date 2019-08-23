---
title: Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923420"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки
В этом примере показано, как создать стандартное [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] диалоговое окно с <xref:System.Windows.Controls.Grid> помощью элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере создается диалоговое окно, такое как диалоговое окно « **Запуск** » в операционной системе Windows.  
  
 В примере создается <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.ColumnDefinition> используются классы и <xref:System.Windows.Controls.RowDefinition> для определения пяти столбцов и четырех строк.  
  
 Затем в примере добавляются и размещается объект <xref:System.Windows.Controls.Image>, `RunIcon.png`, который представляет изображение, найденное в диалоговом окне. Изображение помещается в первый столбец и строку <xref:System.Windows.Controls.Grid> (верхний левый угол).  
  
 Далее в примере добавляется <xref:System.Windows.Controls.TextBlock> элемент в первый столбец, который охватывает оставшиеся столбцы первой строки. Он добавляет еще <xref:System.Windows.Controls.TextBlock> один элемент во вторую строку в первом столбце для представления **открытого** текстового поля. Следующий <xref:System.Windows.Controls.TextBlock> объект представляет область ввода данных.  
  
 Наконец, в примере в последнюю <xref:System.Windows.Controls.Button> строку добавляются три элемента, которые представляют события **ОК**, **Отмена**и **Обзор** .  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Общие сведения о панелях](panels-overview.md)
- [Разделы практического руководства](grid-how-to-topics.md)
