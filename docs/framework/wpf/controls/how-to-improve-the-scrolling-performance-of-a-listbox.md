---
title: Практическое руководство. Улучшение производительности прокрутки ListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: 224b996ad97d9a71ce43023143b68c2ab5b8467b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552796"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a>Практическое руководство. Улучшение производительности прокрутки ListBox
Если <xref:System.Windows.Controls.ListBox> содержит много элементов, ответ пользовательского интерфейса может замедлиться при прокрутке <xref:System.Windows.Controls.ListBox> с помощью колесика мыши или путем перетаскивания ползунка полосы прокрутки. Можно повысить производительность <xref:System.Windows.Controls.ListBox> при прокрутке, задав `VirtualizingStackPanel.VirtualizationMode` присоединенному свойству <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
  
## <a name="description"></a>Описание  
В следующем примере создается <xref:System.Windows.Controls.ListBox> и задает `VirtualizingStackPanel.VirtualizationMode` присоединенному свойству <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> для повышения производительности при прокрутке.  
  
## <a name="code"></a>Код  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 В следующем примере показано данные в предыдущем примере.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
