---
title: "Практическое руководство. Создание элемента сетки"
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
helpviewer_keywords: Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd9614aee6e2bf7085b2fbee77993217439320a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-grid-element"></a>Практическое руководство. Создание элемента сетки
## <a name="example"></a>Пример  
 В следующем примере показано создание и использование экземпляра <xref:System.Windows.Controls.Grid> с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] или кода. В этом примере используется три <xref:System.Windows.Controls.ColumnDefinition> объектов и три <xref:System.Windows.Controls.RowDefinition> объектов для создания сетки, который принимает девять ячеек, как в рабочем листе. Каждая ячейка содержит <xref:System.Windows.Controls.TextBlock> содержит элемент, который представляет данные, а верхняя строка <xref:System.Windows.Controls.TextBlock> с <xref:System.Windows.Controls.Grid.ColumnSpan%2A> применяется свойство. Чтобы отобразить границы каждой ячейки <xref:System.Windows.Controls.Grid.ShowGridLines%2A> включено свойство.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Grid>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
