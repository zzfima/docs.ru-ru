---
title: "Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b7c9d92e4ba58ae5c5f2cbff1c79fd7a3ae673a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms
Процесс добавления элемента в форму Windows Forms <xref:System.Windows.Forms.ListView> управления состоит в определение элемента и назначение ему свойств. Добавление или удаление элементов списка может выполняться в любое время.  
  
### <a name="to-add-items-programmatically"></a>Чтобы добавить элементы программными средствами  
  
1.  Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> метод <xref:System.Windows.Forms.ListView.Items%2A> свойство.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>Чтобы удалить элементы программными средствами  
  
1.  Используйте <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> или <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> метод <xref:System.Windows.Forms.ListView.Items%2A> свойство. <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> Метод удаляет один элемент; <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> метод удаляет все элементы из списка.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListView>  
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
