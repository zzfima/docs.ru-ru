---
title: "Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms"
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
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7283ab53121ecf32fc43593d19121cc843b9c27b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms
Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>. Свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> указывает, имеется ли в наличии строка для ввода новых записей в нижней части элемента управления, свойство <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> указывает, могут ли строки быть удалены. В следующем примере кода используются эти свойства, а также задается свойство <xref:System.Windows.Forms.DataGridView.ReadOnly%2A>, чтобы сделать элемент управления доступным только для чтения.  
  
 Эта задача поддерживается в Visual Studio.  См. также [как: запретить добавление и удаление строк в Windows Forms управления DataGridView с помощью конструктора](http://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>  
 [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
