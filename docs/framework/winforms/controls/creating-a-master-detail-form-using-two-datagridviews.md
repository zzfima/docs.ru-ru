---
title: Пошаговое руководство. Создание формы "основной/подробности" с помощью двух элементов управления Windows Forms DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: 4212c7223aca6a5e7de3189d5f6b2757453cc438
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046092"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Пошаговое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms

Одним из наиболее распространенных сценариев использования <xref:System.Windows.Forms.DataGridView> элемента управления является форма « *основной/подробности* », в которой отображается родительская или дочерняя связь между двумя таблицами базы данных. Выбор строк в главной таблице приводит к обновлению таблицы сведений соответствующими дочерними данными.

Реализовать форму "основной/подробности" легко с помощью взаимодействия между <xref:System.Windows.Forms.DataGridView> элементом управления <xref:System.Windows.Forms.BindingSource> и компонентом. В этом пошаговом руководстве будет построена форма с <xref:System.Windows.Forms.DataGridView> использованием двух элементов <xref:System.Windows.Forms.BindingSource> управления и двух компонентов. В форме будут показаны две связанные таблицы в образце базы данных Northwind SQL Server `Customers` : `Orders`и. По завершении вы получите форму, в которой будут показаны все клиенты в базе данных в главной <xref:System.Windows.Forms.DataGridView> области, а также все заказы выбранного клиента. <xref:System.Windows.Forms.DataGridView>

Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Создайте форму "основной/подробности", используя два элемента](create-a-master-detail-form-using-two-datagridviews.md)управления Windows Forms DataGridView.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения данного пошагового руководства требуется:

- Доступ к серверу с образцом базы данных Northwind SQL Server.

## <a name="creating-the-form"></a>Создание формы

#### <a name="to-create-a-masterdetail-form"></a>Создание формы «основной/подробности»

1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий два <xref:System.Windows.Forms.DataGridView> элемента управления и два <xref:System.Windows.Forms.BindingSource> компонента. Следующий код обеспечивает базовую инициализацию формы и включает `Main` метод. Если вы используете конструктор Visual Studio для создания формы, вместо этого кода можно использовать созданный конструктором код, но обязательно используйте имена, показанные в объявлениях переменных.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных. В этом примере используется `GetData` метод, который заполняет <xref:System.Data.DataSet> объект, добавляет <xref:System.Data.DataRelation> объект в набор данных и связывает <xref:System.Windows.Forms.BindingSource> компоненты. Убедитесь, что переменной `connectionString` присвоено значение, соответствующее базе данных.

    > [!IMPORTANT]
    > Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. Реализуйте обработчик для <xref:System.Windows.Forms.Form.Load> события формы, который привязывает <xref:System.Windows.Forms.DataGridView> элементы управления к <xref:System.Windows.Forms.BindingSource> компонентам и вызывает `GetData` метод. Следующий пример включает в себя код, который изменяет <xref:System.Windows.Forms.DataGridView> размер столбцов в соответствии с отображаемыми данными.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Скомпилируйте и запустите приложение.

  Вы увидите два <xref:System.Windows.Forms.DataGridView> элемента управления: один над другим. В верхней части представлены клиенты из таблицы Northwind `Customers` , а внизу `Orders` — соответствующий выбранному клиенту. При выборе различных строк в верхней <xref:System.Windows.Forms.DataGridView>части соответственно изменяется содержимое нижнего <xref:System.Windows.Forms.DataGridView> изменения.

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
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Создание формы "основной/подробности" с помощью двух элементов управления Windows Forms DataGridView](create-a-master-detail-form-using-two-datagridviews.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
