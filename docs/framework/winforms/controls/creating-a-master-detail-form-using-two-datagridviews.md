---
title: Пошаговое руководство. Создание формы "основной/подробности" с помощью двух элементов управления DataGridView
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
ms.openlocfilehash: bb3da36430c7493b941f3711cb584b4517d5bd54
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740581"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Пример. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms

Одним из наиболее распространенных сценариев использования элемента управления <xref:System.Windows.Forms.DataGridView> является форма « *основной/подробности* », в которой отображается родительская или дочерняя связь между двумя таблицами базы данных. Выбор строк в главной таблице приводит к обновлению таблицы сведений соответствующими дочерними данными.

Реализовать форму "основной/подробности" легко с помощью взаимодействия между элементом управления <xref:System.Windows.Forms.DataGridView> и компонентом <xref:System.Windows.Forms.BindingSource>. В этом пошаговом руководстве будет построена форма с использованием двух элементов управления <xref:System.Windows.Forms.DataGridView> и двух <xref:System.Windows.Forms.BindingSource> компонентов. В форме будут показаны две связанные таблицы в образце базы данных Northwind SQL Server: `Customers` и `Orders`. По завершении вы получите форму, в которой будут показаны все клиенты базы данных в главной <xref:System.Windows.Forms.DataGridView> и все заказы выбранного клиента в подробных <xref:System.Windows.Forms.DataGridView>.

Чтобы скопировать код из этого раздела в виде одного списка, см. раздел [как создать форму "основной/подробности" с помощью двух элементов управления Windows Forms DataGridView](create-a-master-detail-form-using-two-datagridviews.md).

## <a name="prerequisites"></a>предварительные требования

Для выполнения задач этого руководства необходимы:

- Доступ к серверу с образцом базы данных Northwind SQL Server.

## <a name="creating-the-form"></a>Создание формы

#### <a name="to-create-a-masterdetail-form"></a>Создание формы «основной/подробности»

1. Создайте класс, производный от <xref:System.Windows.Forms.Form> и содержащий два элемента управления <xref:System.Windows.Forms.DataGridView> и два <xref:System.Windows.Forms.BindingSource> компонентов. Следующий код обеспечивает базовую инициализацию формы и включает метод `Main`. Если вы используете конструктор Visual Studio для создания формы, вместо этого кода можно использовать созданный конструктором код, но обязательно используйте имена, показанные в объявлениях переменных.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. Реализуйте метод в определении класса формы для обработки сведений о подключении к базе данных. В этом примере используется метод `GetData`, который заполняет объект <xref:System.Data.DataSet>, добавляет объект <xref:System.Data.DataRelation> в набор данных и связывает компоненты <xref:System.Windows.Forms.BindingSource>. Убедитесь, что переменной `connectionString` присвоено значение, соответствующее базе данных.

    > [!IMPORTANT]
    > Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. Реализуйте обработчик для события <xref:System.Windows.Forms.Form.Load> формы, которое привязывает элементы управления <xref:System.Windows.Forms.DataGridView> к <xref:System.Windows.Forms.BindingSource>ным компонентам и вызывает метод `GetData`. Следующий пример включает в себя код, который изменяет размер <xref:System.Windows.Forms.DataGridView> столбцов в соответствии с отображаемыми данными.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Скомпилируйте и запустите приложение.

  Вы увидите два элемента управления <xref:System.Windows.Forms.DataGridView>, один над другим. В верхней части представлены клиенты из таблицы Northwind `Customers`, а внизу — `Orders`, соответствующий выбранному клиенту. При выборе различных строк в верхнем <xref:System.Windows.Forms.DataGridView>содержимое нижнего <xref:System.Windows.Forms.DataGridView> меняется соответствующим образом.

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
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Отображение главного и подчиненного представлений данных с использованием двух элементов управления DataGridView в Windows Forms](create-a-master-detail-form-using-two-datagridviews.md)
- [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md)
