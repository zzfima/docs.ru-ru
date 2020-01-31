---
title: Пошаговое руководство. Проверка данных в элементе управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 45753fb206ad58616c9a727bd81bd2458db6053e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740103"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Пример. Проверка данных элемента управления DataGridView в Windows Forms

При отображении функций ввода данных пользователям часто приходится проверять данные, введенные в форму. Класс <xref:System.Windows.Forms.DataGridView> предоставляет удобный способ выполнения проверки перед фиксацией данных в хранилище данных. Данные можно проверить, обрабатывая событие <xref:System.Windows.Forms.DataGridView.CellValidating>, которое вызывается <xref:System.Windows.Forms.DataGridView> при изменении текущей ячейки.

В этом пошаговом руководстве вы получите строки из таблицы `Customers` образца базы данных Northwind и отобразите их в элементе управления <xref:System.Windows.Forms.DataGridView>. Когда пользователь редактирует ячейку в столбце `CompanyName` и пытается покинуть ячейку, обработчик событий <xref:System.Windows.Forms.DataGridView.CellValidating> проверит строку имени новой компании, чтобы убедиться, что она не пуста. Если новое значение является пустой строкой, <xref:System.Windows.Forms.DataGridView> не позволит курсору пользователя покинуть ячейку, пока не будет введена непустая строка.

Чтобы скопировать код из этого раздела в виде одного списка, см. раздел [как проверить данные в элементе управления Windows Forms DataGridView](how-to-validate-data-in-the-windows-forms-datagridview-control.md).

## <a name="prerequisites"></a>Prerequisites

Для выполнения данного пошагового руководства требуется:

- Доступ к серверу с образцом базы данных Northwind SQL Server.

## <a name="creating-the-form"></a>Создание формы

#### <a name="to-validate-data-entered-in-a-datagridview"></a>Проверка данных, вводимых в элемент DataGridView

1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий элемент управления <xref:System.Windows.Forms.DataGridView> и компонент <xref:System.Windows.Forms.BindingSource>.

    В следующем примере кода показана базовая инициализация и включается метод `Main`.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных.

    В этом примере кода используется метод `GetData`, который возвращает заполненный объект <xref:System.Data.DataTable>. Убедитесь, что для переменной `connectionString` задано значение, подходящее для вашей базы данных.

    > [!IMPORTANT]
    > Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows, также известной как встроенная безопасность, является более безопасным способом управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и настраивает привязку данных.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Реализуйте обработчики для событий <xref:System.Windows.Forms.DataGridView.CellValidating> и <xref:System.Windows.Forms.DataGridView.CellEndEdit> элемента управления <xref:System.Windows.Forms.DataGridView>.

    Обработчик событий <xref:System.Windows.Forms.DataGridView.CellValidating> определяет, является ли значение ячейки в столбце `CompanyName` пустым. Если значение ячейки не проходит проверку, задайте для свойства <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> класса <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> значение `true`. Это приводит к тому, что элемент управления <xref:System.Windows.Forms.DataGridView> запрещает курсору покинуть ячейку. Задайте для свойства <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> в строке пояснительную строку. При этом отображается значок ошибки с подсказкой, содержащей текст ошибки. В обработчике событий <xref:System.Windows.Forms.DataGridView.CellEndEdit> задайте для свойства <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> строки пустую строку. Событие <xref:System.Windows.Forms.DataGridView.CellEndEdit> возникает только в том случае, если ячейка выходит из режима правки, которая не может быть выполнена в случае сбоя проверки.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Скомпилируйте и запустите приложение.

  Вы увидите <xref:System.Windows.Forms.DataGridView> заполненные данными из таблицы `Customers`. Если дважды щелкнуть ячейку в столбце `CompanyName`, можно изменить значение. Если удалить все символы и нажать клавишу TAB, чтобы выйти из ячейки, <xref:System.Windows.Forms.DataGridView> не позволит выйти из нее. При вводе в ячейку непустой строки элемент управления <xref:System.Windows.Forms.DataGridView> позволяет выйти из ячейки.

## <a name="next-steps"></a>Дальнейшие действия

Это приложение предоставляет базовое представление о возможностях элемента управления <xref:System.Windows.Forms.DataGridView>. Внешний вид и поведение элемента управления <xref:System.Windows.Forms.DataGridView> можно настроить несколькими способами.

- Изменение стилей границ и заголовков. Дополнительные сведения см. в разделе [инструкции. изменение стилей границ и линий сетки в элементе управления Windows Forms DataGridView](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Включение или ограничение ввода данных пользователем для элемента управления <xref:System.Windows.Forms.DataGridView>. Дополнительные сведения см. в статьях [как предотвратить добавление и удаление строк в элементе управления Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)и [как сделать столбцы доступны только для чтения в элементе управления Windows Forms DataGridView](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Проверьте введенные пользователем данные на предмет ошибок, связанных с базой данных. Дополнительные сведения см. [в разделе Пошаговое руководство. Обработка ошибок, происходящих во время ввода данных в элементе управления Windows Forms DataGridView](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).

- Обрабатывайте очень большие наборы данных с помощью виртуального режима. Дополнительные сведения см. [в разделе Пошаговое руководство. Реализация виртуального режима в элементе управления Windows Forms DataGridView](implementing-virtual-mode-wf-datagridview-control.md).

- Настройка внешнего вида ячеек. Дополнительные сведения см. в разделе [как настроить внешний вид ячеек в элементе управления Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) и [как задать стили шрифта и цвета в элементе управления Windows Forms DataGridView](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Проверка данных элемента управления DataGridView в Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство. Обработка ошибок, связанных с вводом данных в элемент управления DataGridView, в Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
