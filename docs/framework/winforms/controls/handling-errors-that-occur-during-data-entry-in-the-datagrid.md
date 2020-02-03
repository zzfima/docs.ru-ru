---
title: Пошаговое руководство. Обработка ошибок, происходящих во время ввода данных в элементе управления DataGridView
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
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738734"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Пример. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms

Обработка ошибок из базового хранилища данных является обязательной функцией для приложения ввода данных. Элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> упрощает эту задачу, предоставляя событие <xref:System.Windows.Forms.DataGridView.DataError>, которое возникает, когда хранилище данных обнаруживает нарушение ограничения или бизнес-правило.

В этом пошаговом руководстве вы получите строки из таблицы `Customers` образца базы данных Northwind и отобразите их в элементе управления <xref:System.Windows.Forms.DataGridView>. При обнаружении повторяющегося `CustomerID` значения в новой строке или измененной существующей строке возникает событие <xref:System.Windows.Forms.DataGridView.DataError>, которое будет обрабатываться с помощью <xref:System.Windows.Forms.MessageBox>, описывающего исключение.

Сведения о копировании кода в этом разделе в виде одного списка см. в разделе [как управлять ошибками, происходящими при вводе данных в элементе управления Windows Forms DataGridView](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).

## <a name="prerequisites"></a>предварительные требования

Для выполнения задач этого руководства необходимы:

- Доступ к серверу с образцом базы данных Northwind SQL Server.

## <a name="creating-the-form"></a>Создание формы

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Обработку ошибок ввода данных в элементе управления DataGridView

1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий элемент управления <xref:System.Windows.Forms.DataGridView> и компонент <xref:System.Windows.Forms.BindingSource>.

    В следующем примере кода показана базовая инициализация и включается метод `Main`.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных.

    В этом примере кода используется метод `GetData`, который возвращает заполненный объект <xref:System.Data.DataTable>. Убедитесь, что для переменной `connectionString` задано значение, подходящее для вашей базы данных.

    > [!IMPORTANT]
    > Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и настраивает привязку данных.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. Обработайте событие <xref:System.Windows.Forms.DataGridView.DataError> в <xref:System.Windows.Forms.DataGridView>.

    Если контекст ошибки является операцией фиксации, отобразите ошибку в <xref:System.Windows.Forms.MessageBox>.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Нажмите клавишу F5 для запуска приложения.

  Вы увидите <xref:System.Windows.Forms.DataGridView> элемент управления, заполненный данными из таблицы Customers. Если ввести повторяющееся значение для `CustomerID` и сохранить изменения, значение ячейки будет автоматически отменено, и появится <xref:System.Windows.Forms.MessageBox>, отображающая ошибку ввода данных.

## <a name="next-steps"></a>Next Steps

Это приложение предоставляет базовое представление о возможностях элемента управления <xref:System.Windows.Forms.DataGridView>. Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно настроить несколькими способами.

- Изменение стилей границ и заголовков. Дополнительные сведения см. в разделе [инструкции. изменение стилей границ и линий сетки в элементе управления Windows Forms DataGridView](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Включение или ограничение ввода данных пользователем для элемента управления <xref:System.Windows.Forms.DataGridView>. Дополнительные сведения см. в статьях [как предотвратить добавление и удаление строк в элементе управления Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)и [как сделать столбцы доступны только для чтения в элементе управления Windows Forms DataGridView](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Проверьте введенные пользователем данные в элементе управления <xref:System.Windows.Forms.DataGridView>. Дополнительные сведения см. в разделе [Пошаговое руководство. Проверка данных в элементе управления Windows Forms DataGridView](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).

- Обрабатывайте очень большие наборы данных с помощью виртуального режима. Дополнительные сведения см. [в разделе Пошаговое руководство. Реализация виртуального режима в элементе управления Windows Forms DataGridView](implementing-virtual-mode-wf-datagridview-control.md).

- Настройка внешнего вида ячеек. Дополнительные сведения см. в разделе [как настроить внешний вид ячеек в элементе управления Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) и [как задать стили ячеек по умолчанию для элемента управления Windows Forms DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Пример. Проверка данных элемента управления DataGridView в Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
