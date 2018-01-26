---
title: "Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69dba9b76f823e1779c4555521552b4a423c844c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки
В этом примере показано, как создать стандартную [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] диалоговое окно с помощью <xref:System.Windows.Controls.Grid> элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере создается диалоговое окно такого **запуска** диалоговое окно в [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] операционной системы.  
  
 В примере создается <xref:System.Windows.Controls.Grid> и использует <xref:System.Windows.Controls.ColumnDefinition> и <xref:System.Windows.Controls.RowDefinition> классы для определения пятью столбцами и четырьмя строками.  
  
 Затем в примере добавляются и помещает <xref:System.Windows.Controls.Image>, `RunIcon.png`, для представления изображения, находящийся в диалоговом окне. Изображение размещается в первом столбце и строке <xref:System.Windows.Controls.Grid> (в левом верхнем углу).  
  
 Затем в примере добавляется <xref:System.Windows.Controls.TextBlock> элемента с первым столбцом, который охватывает оставшиеся столбцы первой строки. Он добавляет еще один <xref:System.Windows.Controls.TextBlock> элемент второй строки в первом столбце, для представления **откройте** текстовое поле. Объект <xref:System.Windows.Controls.TextBlock> следующим образом, который представляет область ввода данных.  
  
 Наконец, в примере добавляется три <xref:System.Windows.Controls.Button> в последнюю строку элементы, которые представляют **ОК**, **отменить**, и **Обзор** события.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.GridUnitType>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)
