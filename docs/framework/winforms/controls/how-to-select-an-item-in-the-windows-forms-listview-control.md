---
title: Выбор элемента в элементе управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743234"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Практическое руководство. Выделение строки элемента управления ListView в Windows Forms
В этом примере показано, как программным способом выбрать элемент в элементе управления Windows Forms <xref:System.Windows.Forms.ListView>. При выборе элемента программным способом не происходит автоматического переключения фокуса на элемент управления <xref:System.Windows.Forms.ListView>. По этой причине, как правило, требуется задать элемент в качестве элемента, который будет заменяться при выборе элемента.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- Элемент управления <xref:System.Windows.Forms.ListView> с именем `listView1`, содержащий по крайней мере один элемент.  
  
- Ссылки на пространства имен <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
