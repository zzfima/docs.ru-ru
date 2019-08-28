---
title: Пошаговое руководство. Проверка данных в элементе управления DataGridView в Windows Forms
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
ms.openlocfilehash: 89569feb0cb741f56d09f4e58154b4eecb5a89d4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046381"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Пошаговое руководство. Проверка данных в элементе управления DataGridView в Windows Forms

При отображении функций ввода данных пользователям часто приходится проверять данные, введенные в форму. <xref:System.Windows.Forms.DataGridView> Класс предоставляет удобный способ выполнения проверки перед фиксацией данных в хранилище данных. Данные можно проверить, обрабатывая <xref:System.Windows.Forms.DataGridView.CellValidating> событие, которое вызывается <xref:System.Windows.Forms.DataGridView> при изменении текущей ячейки.

В этом пошаговом руководстве вы получите строки из `Customers` таблицы в образце базы данных Northwind и отобразите их <xref:System.Windows.Forms.DataGridView> в элементе управления. Когда пользователь редактирует ячейку в `CompanyName` столбце и пытается покинуть ячейку <xref:System.Windows.Forms.DataGridView.CellValidating> , обработчик событий проверит новую строку названия компании, чтобы убедиться, что она не пуста. Если новое значение является пустой строкой, то <xref:System.Windows.Forms.DataGridView> будет препятствовать выполнению курсора пользователя. из ячейки, пока не будет указана непустая строка.

Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Проверьте данные в элементе управления](how-to-validate-data-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения данного пошагового руководства требуется:

- Доступ к серверу с образцом базы данных Northwind SQL Server.

## <a name="creating-the-form"></a>Создание формы

#### <a name="to-validate-data-entered-in-a-datagridview"></a>Проверка данных, вводимых в элемент DataGridView

1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и <xref:System.Windows.Forms.DataGridView> содержащий элемент управления и <xref:System.Windows.Forms.BindingSource> компонент.

    Следующий пример кода предоставляет базовую инициализацию и включает `Main` метод.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных.

    В `GetData` этом примере кода используется метод, который возвращает <xref:System.Data.DataTable> заполненный объект. Убедитесь, что для `connectionString` переменной задано значение, подходящее для вашей базы данных.

    > [!IMPORTANT]
    > Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows, также известной как встроенная безопасность, является более безопасным способом управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Реализуйте обработчик для <xref:System.Windows.Forms.Form.Load> события формы, которое инициализирует <xref:System.Windows.Forms.DataGridView> и <xref:System.Windows.Forms.BindingSource> и настраивает привязку данных.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Реализуйте обработчики <xref:System.Windows.Forms.DataGridView> для событий <xref:System.Windows.Forms.DataGridView.CellValidating> элемента <xref:System.Windows.Forms.DataGridView.CellEndEdit> управления и.

    Обработчик событий определяет, является ли значение ячейки `CompanyName` в столбце пустым. <xref:System.Windows.Forms.DataGridView.CellValidating> Если значение ячейки не проходит проверку, задайте <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> для `true`свойства <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> класса значение. Это приводит к <xref:System.Windows.Forms.DataGridView> тому, что элемент управления не покидает ячейку. Задайте для <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> свойства строки пояснительную строку. При этом отображается значок ошибки с подсказкой, содержащей текст ошибки. В обработчике <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> событий присвойте свойству строки пустую строку. <xref:System.Windows.Forms.DataGridView.CellEndEdit> Это <xref:System.Windows.Forms.DataGridView.CellEndEdit> событие возникает только в том случае, если ячейка выходит из режима правки, которая не может быть выполнена в случае сбоя проверки.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Скомпилируйте и запустите приложение.

  Вы увидите <xref:System.Windows.Forms.DataGridView> заполненные данные `Customers` из таблицы. Если дважды щелкнуть ячейку в `CompanyName` столбце, это значение можно изменить. Если удалить все символы и нажать клавишу TAB, чтобы выйти из ячейки, это не <xref:System.Windows.Forms.DataGridView> позволит выйти из нее. При вводе в ячейку <xref:System.Windows.Forms.DataGridView> непустой строки элемент управления позволяет выйти из ячейки.

## <a name="next-steps"></a>Следующие шаги

Это приложение предоставляет базовое представление о <xref:System.Windows.Forms.DataGridView> возможностях элемента управления. Внешний вид и поведение <xref:System.Windows.Forms.DataGridView> элемента управления можно настроить несколькими способами.

- Изменение стилей границ и заголовков. Дополнительные сведения см. в разделе [Практическое руководство. Измените стили границ и линий сетки в элементе управления](change-the-border-and-gridline-styles-in-the-datagrid.md)Windows Forms DataGridView.

- Разрешение или запрет на ввод данных пользователем <xref:System.Windows.Forms.DataGridView> для элемента управления. Дополнительные сведения см. в разделе [Практическое руководство. Предотвращение добавления и удаления строк в элементе управления](prevent-row-addition-and-deletion-datagridview.md)Windows Forms DataGridView и [последующее: Сделать столбцы только для чтения в элементе управления](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

- Проверьте введенные пользователем данные на предмет ошибок, связанных с базой данных. Дополнительные сведения см. в разделе [Пошаговое руководство: Обработка ошибок, происходящих во время ввода данных в элементе управления](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)Windows Forms DataGridView.

- Обрабатывайте очень большие наборы данных с помощью виртуального режима. Дополнительные сведения см. в разделе [Пошаговое руководство: Реализация виртуального режима в элементе управления](implementing-virtual-mode-wf-datagridview-control.md)Windows Forms DataGridView.

- Настройка внешнего вида ячеек. Дополнительные сведения см. в разделе [Практическое руководство. Настройка внешнего вида ячеек в элементе управления](customize-the-appearance-of-cells-in-the-datagrid.md) Windows Forms DataGridView и [выполнение следующих действий: Задайте стили шрифта и цвета в элементе управления](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Ввод данных с помощью элемента управления DataGridView в Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Проверка данных в элементе управления Windows Forms DataGridView](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство: Обработка ошибок, происходящих во время ввода данных в элементе управления Windows Forms DataGridView](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
