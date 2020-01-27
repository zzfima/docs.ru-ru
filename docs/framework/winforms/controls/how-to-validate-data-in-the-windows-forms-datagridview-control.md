---
title: Проверка данных в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: 5fd881829f87fa1dec135d936f22996f196b0594
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728308"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Проверка данных элемента управления DataGridView в Windows Forms
В следующем примере кода показано, как проверить данные, введенные пользователем в элемент управления <xref:System.Windows.Forms.DataGridView>. В этом примере <xref:System.Windows.Forms.DataGridView> заполняется строками из таблицы `Customers` образца базы данных "Northwind". При редактировании ячейки в столбце `CompanyName` проверяется, что ее значение не является пустым. Если обработчик события для <xref:System.Windows.Forms.DataGridView.CellValidating> обнаружит, что значение является пустой строкой, то <xref:System.Windows.Forms.DataGridView> запрещает пользователю выход из ячейки до введения непустой строки.  
  
 Полное описание этого примера кода см. в разделе [Пример. Проверка данных элемента управления DataGridView в Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System, System.Data, System.Windows.Forms и System.XML.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Пример. Проверка данных элемента управления DataGridView в Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
