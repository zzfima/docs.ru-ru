---
title: "Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms"
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
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4895d9fbd84ac00291a717e47102f3d0e04176f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms
В представлении сведений о <xref:System.Windows.Forms.ListView> элемент управления может отображать несколько столбцов для каждого элемента списка. Можно использовать столбцы для отображения пользователю нескольких типов данных о каждом элементе списка. Например в списке файлов можно отображать имя файла, тип файла, размер и Дата последнего изменения файла. Сведения о заполнении столбцов после их создания см. в разделе [как: отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### <a name="to-add-columns-programmatically"></a>Чтобы добавить столбцы программными средствами  
  
1.  Задайте в качестве <xref:System.Windows.Forms.ListView.View%2A> свойства <xref:System.Windows.Forms.View.Details>.  
  
2.  Используйте <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> метода в представлении списка <xref:System.Windows.Forms.ListView.Columns%2A> свойство.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListView>  
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
