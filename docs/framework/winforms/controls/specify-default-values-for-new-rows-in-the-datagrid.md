---
title: Указание значений по умолчанию для новых строк в элементе управления DataGridView
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
ms.openlocfilehash: 364f922aefc10e57f2ed7f3a0c2a5b25c922d87a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742930"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Определение значений по умолчанию для новых строк элемента управления DataGridView в Windows Forms
Вы можете сделать ввод данных более удобным, когда приложение заполнит значения по умолчанию для вновь добавленных строк. С помощью класса <xref:System.Windows.Forms.DataGridView> можно заполнить значения по умолчанию с помощью события <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>. Это событие возникает, когда пользователь вводит строку для новых записей. Когда код обрабатывает это событие, можно заполнить нужные ячейки значениями по своему усмотрению.  
  
 В следующем примере кода показано, как задать значения по умолчанию для новых строк с помощью события <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;  
  
- Функция `NewCustomerId` для создания уникальных значений `CustomerID`.  
  
- ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
