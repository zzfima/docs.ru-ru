---
title: Создание непривязанного элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740173"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Пример. Создание не связанного с данными элемента управления DataGridView в Windows Forms
Часто может потребоваться отобразить табличные данные, которые не берутся из базы данных. Например, может потребоваться отобразить содержимое двумерного массива строк. Класс <xref:System.Windows.Forms.DataGridView> предоставляет простой и настраиваемый способ вывода данных без привязки к источнику данных. В этом пошаговом руководстве показано, как заполнить элемент управления <xref:System.Windows.Forms.DataGridView> и управлять добавлением и удалением строк в "несвязанном" режиме. По умолчанию пользователь может добавлять новые строки. Чтобы предотвратить добавление строк, задайте для свойства <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> значение `false`.  
  
 Чтобы скопировать код из этого раздела в виде одного списка, см. раздел [как создать несвязанный Windows Forms элемент управления DataGridView](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Создание формы  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Использование непривязанного элемента управления DataGridView  
  
1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий следующие объявления переменных и метод `Main`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. Реализуйте метод `SetupLayout` в определении класса формы, чтобы настроить макет формы.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. Создайте `SetupDataGridView` метод для настройки <xref:System.Windows.Forms.DataGridView> столбцов и свойств.  
  
     Этот метод сначала добавляет элемент управления <xref:System.Windows.Forms.DataGridView> в коллекцию <xref:System.Windows.Forms.Control.Controls%2A> формы. Затем число отображаемых столбцов задается с помощью свойства <xref:System.Windows.Forms.DataGridView.ColumnCount%2A>. Стиль по умолчанию для заголовков столбцов задается установкой свойств <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>и <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращаемых свойством <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>.  
  
     Задаются свойства макета и внешнего вида, а затем имена столбцов присваиваются. При выходе из этого метода элемент управления <xref:System.Windows.Forms.DataGridView> готов к заполнению.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. Создайте `PopulateDataGridView` метод, чтобы добавить строки в элемент управления <xref:System.Windows.Forms.DataGridView>.  
  
     Каждая строка представляет композицию и связанную с ней информацию.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. С помощью вспомогательных методов можно присоединять обработчики событий.  
  
     Вы будете выполнять обработку событий <xref:System.Windows.Forms.Control.Click> кнопок " **Добавить** " и " **удалить** ", <xref:System.Windows.Forms.Form.Load> события формы и события <xref:System.Windows.Forms.DataGridView.CellFormatting> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
     При возникновении события <xref:System.Windows.Forms.Control.Click> кнопки " **Добавить** " в <xref:System.Windows.Forms.DataGridView>добавляется новая пустая строка.  
  
     При возникновении события <xref:System.Windows.Forms.Control.Click> кнопки " **Удалить** " выбранная строка удаляется, если это не строка для новых записей, что позволяет пользователю добавлять новые строки. Эта строка всегда является последней строкой в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
     При возникновении события <xref:System.Windows.Forms.Form.Load> формы вызываются служебные методы `SetupLayout`, `SetupDataGridView`и `PopulateDataGridView`.  
  
     При возникновении события <xref:System.Windows.Forms.DataGridView.CellFormatting> каждая ячейка в столбце `Date` форматируется как длинная Дата, если только не удается выполнить синтаксический анализ значения ячейки.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.  
  
#### <a name="to-test-the-form"></a>Тестирование формы  
  
- Нажмите клавишу F5 для запуска приложения.  
  
     Вы увидите элемент управления <xref:System.Windows.Forms.DataGridView>, в котором отображаются песни, перечисленные в `PopulateDataGridView`. Можно добавлять новые строки с помощью кнопки **Добавить строку** , а также удалять выбранные строки с помощью кнопки **Удалить строку** . Несвязанным элементом управления <xref:System.Windows.Forms.DataGridView> является хранилище данных, и его данные не зависят от любого внешнего источника, например <xref:System.Data.DataSet> или массива.  
  
## <a name="next-steps"></a>Next Steps  
 Это приложение предоставляет базовое представление о возможностях элемента управления <xref:System.Windows.Forms.DataGridView>. Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно настроить несколькими способами.  
  
- Изменение стилей границ и заголовков. Дополнительные сведения см. в разделе [инструкции. изменение стилей границ и линий сетки в элементе управления Windows Forms DataGridView](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
- Включение или ограничение ввода данных пользователем для элемента управления <xref:System.Windows.Forms.DataGridView>. Дополнительные сведения см. в статьях [как предотвратить добавление и удаление строк в элементе управления Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)и [как сделать столбцы доступны только для чтения в элементе управления Windows Forms DataGridView](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
- Проверьте введенные пользователем данные на предмет ошибок, связанных с базой данных. Дополнительные сведения см. [в разделе Пошаговое руководство. Обработка ошибок, происходящих во время ввода данных в элементе управления Windows Forms DataGridView](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
- Обрабатывайте очень большие наборы данных с помощью виртуального режима. Дополнительные сведения см. [в разделе Пошаговое руководство. Реализация виртуального режима в элементе управления Windows Forms DataGridView](implementing-virtual-mode-wf-datagridview-control.md).  
  
- Настройка внешнего вида ячеек. Дополнительные сведения см. в разделе [как настроить внешний вид ячеек в элементе управления Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) и [как задать стили ячеек по умолчанию для элемента управления Windows Forms DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Создание не связанного с данными элемента управления DataGridView в Windows Forms](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Режимы отображения данных в элементе управления DataGridView в Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
