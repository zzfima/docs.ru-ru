---
title: Обработку ошибок, происходящих во время ввода данных в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 03a13957c80b0ab62afb11efc57cf31e059e5942
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745616"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms
В примере кода ниже показано, как использовать элемент управления <xref:System.Windows.Forms.DataGridView> для сообщения пользователю об ошибках ввода данных.  
  
 Полное описание этого примера кода см. в разделе [Пошаговое руководство. Обработка ошибок, возникающих во время ввода данных в элементе управления Windows Forms DataGridView](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System, System.Data, System.Windows.Forms и System.XML.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Пошаговое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Пример. Проверка данных элемента управления DataGridView в Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
