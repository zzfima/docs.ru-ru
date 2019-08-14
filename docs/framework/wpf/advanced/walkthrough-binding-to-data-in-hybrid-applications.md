---
title: Пошаговое руководство. Привязка к данным в гибридных приложениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: ef5f14cdbecab8bc780cb7b2a642429970a25316
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972280"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Пошаговое руководство. Привязка к данным в гибридных приложениях

Привязка источника данных к элементу управления необходима для предоставления пользователям доступа к базовым данным независимо от того, используется [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] В этом пошаговом руководстве показано, как можно использовать привязку данных в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] гибридных приложениях, включающих как элементы управления, так и. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта.

- Определение шаблона данных.

- Задание макета формы.

- Задание привязок данных.

- Отображение данных с помощью взаимодействия.

- Добавление источника данных в проект.

- Подключение к источнику данных.

Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Пример привязки данных в гибридных приложениях](https://go.microsoft.com/fwlink/?LinkID=159983).

Изучив этот раздел, вы будете иметь представление о функциях привязки данных в гибридных приложениях.

## <a name="prerequisites"></a>Предварительные требования

Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Visual Studio.

- Доступ к учебной базе данных Northwind, выполняемой на Microsoft SQL Server.

## <a name="creating-the-project"></a>Создание проекта

### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта

1. Создайте проект приложения WPF с именем `WPFWithWFAndDatabinding`.

2. В обозревателе решений добавьте ссылки на следующие сборки.

    - WindowsFormsIntegration

    - System.Windows.Forms.

3. Откройте файл MainWindow. XAML в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

4. В элементе добавьте следующее [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространств имен. <xref:System.Windows.Window>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Присвойте <xref:System.Windows.Controls.Grid> элементу `mainGrid` имя по умолчанию, назначив <xref:System.Windows.FrameworkElement.Name%2A> свойство.

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a>Определение шаблона данных

Главный список клиентов отображается в <xref:System.Windows.Controls.ListBox> элементе управления. В следующем примере кода определяется <xref:System.Windows.DataTemplate> объект с именем `ListItemsTemplate` , который управляет визуальным деревом <xref:System.Windows.Controls.ListBox> элемента управления. Это <xref:System.Windows.DataTemplate> значение присваивается <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойству элемента управления.

### <a name="to-define-the-data-template"></a>Чтобы определить шаблон данных, выполните следующие действия.

- Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a>Задание макета формы

Макет формы определяется сеткой с тремя строками и тремя столбцами. <xref:System.Windows.Controls.Label>для поиска каждого столбца в таблице Customers предусмотрены элементы управления.

### <a name="to-set-up-the-grid-layout"></a>Настройка макета сетки

- Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a>Чтобы настроить элементы управления Label, выполните следующие действия.

- Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a>Задание привязок данных

Главный список клиентов отображается в <xref:System.Windows.Controls.ListBox> элементе управления. Присоединенная `ListItemsTemplate` привязка привязывает <xref:System.Windows.Controls.TextBlock> элемент управления к `ContactName` полю из базы данных.

Сведения о каждой записи клиента отображаются в нескольких <xref:System.Windows.Controls.TextBox> элементах управления.

### <a name="to-specify-data-bindings"></a>Чтобы задать привязки данных, выполните следующие действия.

- Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.

     Класс привязывает <xref:System.Windows.Controls.TextBox> элементы управления к соответствующим полям в базе данных. <xref:System.Windows.Data.Binding>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a>Отображение данных с помощью взаимодействия

Заказы, соответствующие выбранному клиенту, отображаются в <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> элементе управления с именем. `dataGridView1` `dataGridView1` Элемент управления привязан к источнику данных в файле кода программной части. Элемент управления является родительским для этого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления. <xref:System.Windows.Forms.Integration.WindowsFormsHost>

### <a name="to-display-data-in-the-datagridview-control"></a>Чтобы отобразить данные в элементе управления DataGridView, выполните следующие действия.

- Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a>Добавление источника данных в проект

С помощью Visual Studio можно легко добавить в проект источник данных. Эта процедура добавляет строго типизированный набор данных в ваш проект. Также добавляется несколько других классов поддержки, таких как адаптеры таблиц для каждой из выбранных таблиц.

### <a name="to-add-the-data-source"></a>Добавление источника данных

1. В меню **данные** выберите команду **Добавить новый источник данных**.

2. В **мастере настройки источника данных**создайте подключение к базе данных Northwind с помощью набора данных. Дополнительные сведения см. в разделе [Практическое руководство. Подключение к данным в базе данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).

3. При появлении запроса в **мастере настройки источника данных**сохраните строку подключения как `NorthwindConnectionString`.

4. Когда появится запрос на выбор объектов базы данных, выберите `Customers` таблицы и `Orders` и назовите созданный набор `NorthwindDataSet`данных.

## <a name="binding-to-the-data-source"></a>Подключение к источнику данных

<xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Компонент предоставляет единый интерфейс для источника данных приложения. Привязка к источнику данных реализована в файле кода программной части.

### <a name="to-bind-to-the-data-source"></a>Чтобы создать привязку к источнику данных, выполните следующие действия.

1. Откройте файл кода программной части с именем MainWindow.xaml.vb или MainWindow.xaml.cs.

2. Скопируйте следующий код в `MainWindow` определение класса.

     Этот код объявляет <xref:System.Windows.Forms.BindingSource> компонент и связанные вспомогательные классы, подключающиеся к базе данных.

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. Копируйте в конструктор следующий код.

     Этот код создает и инициализирует <xref:System.Windows.Forms.BindingSource> компонент.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. Откройте файл MainWindow.xaml.

5. В представление конструирования или представлении XAML выберите <xref:System.Windows.Window> элемент.

6. В окно свойств перейдите на вкладку **события** .

7. Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событие.

8. Скопируйте следующий код в <xref:System.Windows.FrameworkElement.Loaded> обработчик событий.

     Этот код назначает <xref:System.Windows.Forms.BindingSource> компонент в качестве контекста данных и заполняет `Customers` объекты адаптера и `Orders` .

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Скопируйте следующий код в `MainWindow` определение класса.

     Этот метод обрабатывает <xref:System.Windows.Data.CollectionView.CurrentChanged> событие и обновляет текущий элемент привязки данных.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Пример привязки данных в гибридных приложениях](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Пошаговое руководство: Размещение составного элемента управления Windows Forms в WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
