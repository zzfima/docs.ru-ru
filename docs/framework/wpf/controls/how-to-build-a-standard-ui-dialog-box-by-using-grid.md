---
title: Как выполнить Построение стандартного диалогового окна пользовательского интерфейса с помощью сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 893b3f7fda3314b158f7c67392a0913e30a92c09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650526"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Как выполнить Построение стандартного диалогового окна пользовательского интерфейса с помощью сетки
В этом примере показано, как создать стандартную [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] диалоговое окно с помощью <xref:System.Windows.Controls.Grid> элемент.  
  
## <a name="example"></a>Пример  
 В следующем примере создается диалоговое окно, похожее **запуска** диалогового окна в [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] операционной системы.  
  
 В примере создается <xref:System.Windows.Controls.Grid> и использует <xref:System.Windows.Controls.ColumnDefinition> и <xref:System.Windows.Controls.RowDefinition> классам определять пятью столбцами и четырьмя строками.  
  
 Затем добавляет и помещает <xref:System.Windows.Controls.Image>, `RunIcon.png`, чтобы представить образ, который находится в диалоговом окне. Изображение размещается в первом столбце и строке <xref:System.Windows.Controls.Grid> (в левом верхнем углу).  
  
 Затем в примере добавляется <xref:System.Windows.Controls.TextBlock> элемент в первый столбец, который охватывает оставшиеся столбцы первой строки. Он добавляет другой <xref:System.Windows.Controls.TextBlock> элемент второй строки в первом столбце, для представления **откройте** текстовое поле. Объект <xref:System.Windows.Controls.TextBlock> с помощью которой представляет область ввода данных.  
  
 Наконец, в примере добавляется три <xref:System.Windows.Controls.Button> элементов в последнюю строку, которые представляют **ОК**, **отменить**, и **Обзор** события.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
