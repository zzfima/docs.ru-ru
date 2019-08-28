---
title: Пошаговое руководство. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms
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
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: cee6fe3b049378fa7bbe2585a3607049eaf231bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046079"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Пошаговое руководство. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms

Обработка ошибок из базового хранилища данных является обязательной функцией для приложения ввода данных. Элемент управления <xref:System.Windows.Forms.DataGridView> Windows Forms делает это простым, предоставляя <xref:System.Windows.Forms.DataGridView.DataError> событие, которое возникает, когда хранилище данных обнаруживает нарушение ограничения или бизнес-правило.

В этом пошаговом руководстве вы получите строки из `Customers` таблицы в образце базы данных Northwind и отобразите их <xref:System.Windows.Forms.DataGridView> в элементе управления. При обнаружении `CustomerID` повторяющегося значения в новой строке или измененной существующей строке <xref:System.Windows.Forms.DataGridView.DataError> возникает событие, которое будет обработано отображением <xref:System.Windows.Forms.MessageBox> , описывающим исключение.

Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Обрабатывайте ошибки, возникающие при вводе данных в элементе](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)управления Windows Forms DataGridView.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения данного пошагового руководства требуется:

- Доступ к серверу с образцом базы данных Northwind SQL Server.

## <a name="creating-the-form"></a>Создание формы

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Обработку ошибок ввода данных в элементе управления DataGridView

1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и <xref:System.Windows.Forms.DataGridView> содержащий элемент управления и <xref:System.Windows.Forms.BindingSource> компонент.

    Следующий пример кода предоставляет базовую инициализацию и включает `Main` метод.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных.

    В `GetData` этом примере кода используется метод, который возвращает <xref:System.Data.DataTable> заполненный объект. Убедитесь, что для `connectionString` переменной задано значение, подходящее для вашей базы данных.

    > [!IMPORTANT]
    > Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. Реализуйте обработчик для <xref:System.Windows.Forms.Form.Load> события формы, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и настраивает привязку данных.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. Обработайте <xref:System.Windows.Forms.DataGridView>событиев <xref:System.Windows.Forms.DataGridView.DataError> .

    Если контекст ошибки является операцией фиксации, отобразите ошибку в <xref:System.Windows.Forms.MessageBox>.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Нажмите клавишу F5 для запуска приложения.

  Вы увидите <xref:System.Windows.Forms.DataGridView> элемент управления, заполненный данными из таблицы Customers. Если ввести повторяющееся значение для `CustomerID` и сохранить изменения, значение ячейки будет автоматически отменено, и <xref:System.Windows.Forms.MessageBox> появится сообщение, отображающее ошибку ввода данных.

## <a name="next-steps"></a>Следующие шаги

Это приложение предоставляет базовое представление о <xref:System.Windows.Forms.DataGridView> возможностях элемента управления. Внешний вид и поведение <xref:System.Windows.Forms.DataGridView> элемента управления можно настроить несколькими способами.

- Изменение стилей границ и заголовков. Дополнительные сведения см. в разделе [Практическое руководство. Измените стили границ и линий сетки в элементе управления](change-the-border-and-gridline-styles-in-the-datagrid.md)Windows Forms DataGridView.

- Разрешение или запрет на ввод данных пользователем <xref:System.Windows.Forms.DataGridView> для элемента управления. Дополнительные сведения см. в разделе [Практическое руководство. Предотвращение добавления и удаления строк в элементе управления](prevent-row-addition-and-deletion-datagridview.md)Windows Forms DataGridView и [последующее: Сделать столбцы только для чтения в элементе управления](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

- Проверка входных данных пользователя <xref:System.Windows.Forms.DataGridView> для элемента управления. Дополнительные сведения см. в разделе [Пошаговое руководство: Проверка данных в элементе управления](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

- Обрабатывайте очень большие наборы данных с помощью виртуального режима. Дополнительные сведения см. в разделе [Пошаговое руководство: Реализация виртуального режима в элементе управления](implementing-virtual-mode-wf-datagridview-control.md)Windows Forms DataGridView.

- Настройка внешнего вида ячеек. Дополнительные сведения см. в разделе [Практическое руководство. Настройка внешнего вида ячеек в элементе управления](customize-the-appearance-of-cells-in-the-datagrid.md) Windows Forms DataGridView и [выполнение следующих действий: Задайте стили ячеек по умолчанию для элемента управления](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Обработку ошибок, происходящих во время ввода данных в элементе управления Windows Forms DataGridView](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Пошаговое руководство: Проверка данных в элементе управления Windows Forms DataGridView](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
