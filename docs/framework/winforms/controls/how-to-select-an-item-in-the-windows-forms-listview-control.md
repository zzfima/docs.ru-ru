---
title: Как выполнить Выберите элемент в элементе управления ListView формы Windows
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
ms.openlocfilehash: ed3e68fbe77f194ed04d15f99a48657a32a13b50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644720"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Как выполнить Выберите элемент в элементе управления ListView формы Windows
В этом примере показано, как программно выбрать элемент в формах Windows <xref:System.Windows.Forms.ListView> элемента управления. Выбор элемента программным образом не изменяется автоматически фокуса в <xref:System.Windows.Forms.ListView> элемента управления. По этой причине обычно необходимо также задать элемент как с фокусом ввода при выделении элемента.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Объект <xref:System.Windows.Forms.ListView> управления с именем `listView1` , содержащий хотя бы один элемент.  
  
-   Ссылки на пространства имен <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
