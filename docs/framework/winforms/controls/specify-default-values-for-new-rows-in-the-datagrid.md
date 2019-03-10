---
title: Практическое руководство. Определение значения по умолчанию для новых строк в элементе управления DataGridView Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: cc854f0cdbef8373b74a16c7d5bc044cfee5aa84
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708032"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Определение значения по умолчанию для новых строк в элементе управления DataGridView Windows Forms
Ввод данных можно сделать более удобным при приложение по умолчанию заполняет значения для только что добавленных строк. С помощью <xref:System.Windows.Forms.DataGridView> класса, можно заполнять в используемом по умолчанию значения с <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий. Это событие возникает, когда пользователь вводит строку для новых записей. Когда ваш код обрабатывает это событие, можно заполнить требуемые ячейки со значениями по своему выбору.  
  
 В следующем примере кода демонстрируется указание значений по умолчанию для новых строк с помощью <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> событий.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
-   Объект `NewCustomerId` функция для создания уникальных `CustomerID` значения.  
  
-   ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
