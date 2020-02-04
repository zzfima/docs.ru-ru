---
title: Предотвращение добавления и удаления строк в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: de8e0412faf8c3731f9356771b35a4a5d31b6ec7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728718"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms
Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>. Свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> указывает, имеется ли в наличии строка для ввода новых записей в нижней части элемента управления, свойство <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> указывает, могут ли строки быть удалены. В следующем примере кода используются эти свойства, а также задается свойство <xref:System.Windows.Forms.DataGridView.ReadOnly%2A>, чтобы сделать элемент управления доступным только для чтения.  
  
 Эта задача поддерживается в Visual Studio. См. также раздел [как предотвратить добавление и удаление строк в элементе управления Windows Forms DataGridView с помощью конструктора](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
