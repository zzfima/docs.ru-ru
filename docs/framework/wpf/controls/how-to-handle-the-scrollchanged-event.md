---
title: Как выполнить Обработка события ScrollChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], raising ScrollChanged events
- ScrollChanged events [WPF]
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
ms.openlocfilehash: b38effc9e32a5d13a0556b345bc0be25e81e0036
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711750"
---
# <a name="how-to-handle-the-scrollchanged-event"></a>Как выполнить Обработка события ScrollChanged
## <a name="example"></a>Пример  
 В этом примере демонстрируется обработка <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> событие <xref:System.Windows.Controls.ScrollViewer>.  
  
 Объект <xref:System.Windows.Documents.FlowDocument> элемент с <xref:System.Windows.Documents.Paragraph> определить компоненты в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Когда <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> событие возникает из-за взаимодействия с пользователем, вызывается обработчик и текст записывается <xref:System.Windows.Controls.TextBlock> означает, что возникло событие.  
  
 [!code-xaml[scrollchangedeventargsLayout#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>
- <xref:System.Windows.Controls.ScrollChangedEventHandler>
- <xref:System.Windows.Controls.ScrollChangedEventArgs>
