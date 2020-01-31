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
ms.openlocfilehash: 1bb38436049e338ab6033ae3b6370732a457d520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794225"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Пошаговое руководство. Привязка к данным в гибридных приложениях

Привязка источника данных к элементу управления необходима для предоставления пользователям доступа к базовым данным независимо от того, используется Windows Forms или [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В этом пошаговом руководстве показано, как можно использовать привязку данных в гибридных приложениях, включающих как Windows Forms, так и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ные элементы управления.

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

## <a name="prerequisites"></a>Prerequisites

Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Visual Studio.

- Доступ к учебной базе данных Northwind, выполняемой на Microsoft SQL Server.

## <a name="creating-the-project"></a>Создание проекта

### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта

1. Создайте проект приложения WPF с именем `WPFWithWFAndDatabinding`.

2. В обозревателе решений добавьте ссылки на следующие сборки.

    - WindowsFormsIntegration

    - System.Windows.Forms.

3. Откройте файл MainWindow. XAML в конструкторе WPF.

4. В элементе <xref:System.Windows.Window> добавьте следующее сопоставление пространств имен Windows Forms.

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Присвойте элементу <xref:System.Windows.Controls.Grid> по умолчанию `mainGrid`, назначив свойство <xref:System.Windows.FrameworkElement.Name%2A>.

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a>Определение шаблона данных

Главный список клиентов отображается в элементе управления <xref:System.Windows.Controls.ListBox>. В следующем примере кода определяется объект <xref:System.Windows.DataTemplate> с именем `ListItemsTemplate`, который управляет визуальным деревом элемента управления <xref:System.Windows.Controls.ListBox>. Этот <xref:System.Windows.DataTemplate> присваивается свойству <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> элемента управления <xref:System.Windows.Controls.ListBox>.

### <a name="to-define-the-data-template"></a>Чтобы определить шаблон данных, выполните следующие действия.

- Скопируйте следующий код XAML в объявление элемента <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a>Задание макета формы

Макет формы определяется сеткой с тремя строками и тремя столбцами. для поиска каждого столбца в таблице Customers предусмотрены <xref:System.Windows.Controls.Label> элементы управления.

### <a name="to-set-up-the-grid-layout"></a>Настройка макета сетки

- Скопируйте следующий код XAML в объявление элемента <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a>Чтобы настроить элементы управления Label, выполните следующие действия.

- Скопируйте следующий код XAML в объявление элемента <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a>Задание привязок данных

Главный список клиентов отображается в элементе управления <xref:System.Windows.Controls.ListBox>. Присоединенный `ListItemsTemplate` привязывает <xref:System.Windows.Controls.TextBlock> элемент управления к полю `ContactName` из базы данных.

Сведения о каждой записи клиента отображаются в нескольких элементах управления <xref:System.Windows.Controls.TextBox>.

### <a name="to-specify-data-bindings"></a>Чтобы задать привязки данных, выполните следующие действия.

- Скопируйте следующий код XAML в объявление элемента <xref:System.Windows.Controls.Grid>.

     Класс <xref:System.Windows.Data.Binding> привязывает элементы управления <xref:System.Windows.Controls.TextBox> к соответствующим полям в базе данных.

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a>Отображение данных с помощью взаимодействия

Заказы, соответствующие выбранному клиенту, отображаются в элементе управления <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> с именем `dataGridView1`. Элемент управления `dataGridView1` привязан к источнику данных в файле кода программной части. Элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> является родительским для этого элемента управления Windows Forms.

### <a name="to-display-data-in-the-datagridview-control"></a>Чтобы отобразить данные в элементе управления DataGridView, выполните следующие действия.

- Скопируйте следующий код XAML в объявление элемента <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a>Добавление источника данных в проект

С помощью Visual Studio можно легко добавить в проект источник данных. Эта процедура добавляет строго типизированный набор данных в ваш проект. Также добавляется несколько других классов поддержки, таких как адаптеры таблиц для каждой из выбранных таблиц.

### <a name="to-add-the-data-source"></a>Добавление источника данных

1. В меню **данные** выберите команду **Добавить новый источник данных**.

2. В **мастере настройки источника данных**создайте подключение к базе данных Northwind с помощью набора данных. Дополнительные сведения см. в разделе [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).

3. При появлении запроса в **мастере настройки источника данных**сохраните строку подключения как `NorthwindConnectionString`.

4. При появлении запроса на выбор объектов базы данных выберите таблицы `Customers` и `Orders` и присвойте созданному набору данных имя `NorthwindDataSet`.

## <a name="binding-to-the-data-source"></a>Подключение к источнику данных

Компонент <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> предоставляет унифицированный интерфейс для источника данных приложения. Привязка к источнику данных реализована в файле кода программной части.

### <a name="to-bind-to-the-data-source"></a>Чтобы создать привязку к источнику данных, выполните следующие действия.

1. Откройте файл кода программной части с именем MainWindow.xaml.vb или MainWindow.xaml.cs.

2. Скопируйте следующий код в определение класса `MainWindow`.

     Этот код объявляет компонент <xref:System.Windows.Forms.BindingSource> и связанные вспомогательные классы, которые подключаются к базе данных.

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. Копируйте в конструктор следующий код.

     Этот код создает и инициализирует компонент <xref:System.Windows.Forms.BindingSource>.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. Откройте файл MainWindow.xaml.

5. В представление конструирования или представлении XAML выберите элемент <xref:System.Windows.Window>.

6. В окно свойств перейдите на вкладку **события** .

7. Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.

8. Скопируйте следующий код в обработчик событий <xref:System.Windows.FrameworkElement.Loaded>.

     Этот код назначает компонент <xref:System.Windows.Forms.BindingSource> в качестве контекста данных и заполняет объекты адаптера `Customers` и `Orders`.

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Скопируйте следующий код в определение класса `MainWindow`.

     Этот метод обрабатывает событие <xref:System.Windows.Data.CollectionView.CurrentChanged> и обновляет текущий элемент привязки данных.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. Нажмите клавишу F5 для построения и запуска приложения.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пример привязки данных в гибридных приложениях](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
