---
title: "Пошаговое руководство. Привязка к данным в гибридных приложениях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 957559cbc88855700471cc457f76d69ef5a296d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Пошаговое руководство. Привязка к данным в гибридных приложениях
Привязка источника данных к элементу управления необходима для предоставления пользователям доступа к базовым данным независимо от использовании [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В этом пошаговом руководстве показано, как можно использовать привязку данных в гибридных приложениях, содержащих [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта.  
  
-   Определение шаблона данных.  
  
-   Задание макета формы.  
  
-   Задание привязок данных.  
  
-   Отображение данных с помощью взаимодействия.  
  
-   Добавление источника данных в проект.  
  
-   Подключение к источнику данных.  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [привязка данных в гибридных приложениях-пример](http://go.microsoft.com/fwlink/?LinkID=159983).  
  
 Изучив этот раздел, вы будете иметь представление о функциях привязки данных в гибридных приложениях.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Доступ к учебной базе данных Northwind, под управлением Microsoft SQL Server.  
  
## <a name="creating-the-project"></a>Создание проекта  
  
#### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта  
  
1.  Создание проекта приложения WPF с именем `WPFWithWFAndDatabinding`.  
  
2.  В обозревателе решений добавьте ссылки на следующие сборки.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms.  
  
3.  Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  В <xref:System.Windows.Window> элемента, добавьте следующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространства имен.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Имя по умолчанию <xref:System.Windows.Controls.Grid> элемент `mainGrid` , назначив <xref:System.Windows.FrameworkElement.Name%2A> свойство.  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a>Определение шаблона данных  
 Основной список клиентов отображается в <xref:System.Windows.Controls.ListBox> элемента управления. В следующем примере кода определяется <xref:System.Windows.DataTemplate> объект с именем `ListItemsTemplate` визуального дерева, который управляет <xref:System.Windows.Controls.ListBox> элемента управления. Это <xref:System.Windows.DataTemplate> назначается <xref:System.Windows.Controls.ListBox> элемента управления <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство.  
  
#### <a name="to-define-the-data-template"></a>Чтобы определить шаблон данных, выполните следующие действия.  
  
-   Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a>Задание макета формы  
 Макет формы определяется сеткой с тремя строками и тремя столбцами. <xref:System.Windows.Controls.Label>элементы управления предоставляются для идентификации каждого столбца в таблице Customers.  
  
#### <a name="to-set-up-the-grid-layout"></a>Настройка макета сетки  
  
-   Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a>Чтобы настроить элементы управления Label, выполните следующие действия.  
  
-   Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a>Задание привязок данных  
 Основной список клиентов отображается в <xref:System.Windows.Controls.ListBox> элемента управления. Прикрепленное `ListItemsTemplate` привязывает <xref:System.Windows.Controls.TextBlock> управления `ContactName` поля из базы данных.  
  
 Подробные сведения о каждой записи клиента отображаются в нескольких <xref:System.Windows.Controls.TextBox> элементов управления.  
  
#### <a name="to-specify-data-bindings"></a>Чтобы задать привязки данных, выполните следующие действия.  
  
-   Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.  
  
     <xref:System.Windows.Data.Binding> Класса привязки <xref:System.Windows.Controls.TextBox> элементов управления с соответствующими полями в базе данных.  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a>Отображение данных с помощью взаимодействия  
 Заказы, соответствующие выбранному заказчику, отображаются в <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> управления с именем `dataGridView1`. `dataGridView1` Элемент управления привязан к источнику данных в файле кода. Объект <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления является родительским для данного [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.  
  
#### <a name="to-display-data-in-the-datagridview-control"></a>Чтобы отобразить данные в элементе управления DataGridView, выполните следующие действия.  
  
-   Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> объявление элемента.  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a>Добавление источника данных в проект  
 С [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно легко добавить источник данных к проекту. Эта процедура добавляет строго типизированный набор данных в ваш проект. Также добавляется несколько других классов поддержки, таких как адаптеры таблиц для каждой из выбранных таблиц.  
  
#### <a name="to-add-the-data-source"></a>Добавление источника данных  
  
1.  Из **данные** последовательно выберите пункты **добавить новый источник данных**.  
  
2.  В **мастер настройки источника данных**, создать подключение к базе данных Northwind с помощью набора данных. Дополнительные сведения см. в разделе [как: подключение к данным в базе данных](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).  
  
3.  При появлении по **мастер настройки источника данных**, сохранить строку подключения в качестве `NorthwindConnectionString`.  
  
4.  При появлении запроса на выбор объектов базы данных выберите `Customers` и `Orders` таблицы и имя созданного набора данных `NorthwindDataSet`.  
  
## <a name="binding-to-the-data-source"></a>Подключение к источнику данных  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Компонент предоставляет единый интерфейс для источника данных приложения. Привязка к источнику данных реализована в файле кода программной части.  
  
#### <a name="to-bind-to-the-data-source"></a>Чтобы создать привязку к источнику данных, выполните следующие действия.  
  
1.  Откройте файл кода программной части с именем MainWindow.xaml.vb или MainWindow.xaml.cs.  
  
2.  Скопируйте следующий код в `MainWindow` определения класса.  
  
     Этот код объявляет <xref:System.Windows.Forms.BindingSource> компонента и связанные вспомогательные классы, которые подключаются к базе данных.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  Копируйте в конструктор следующий код.  
  
     Этот код создает и инициализирует <xref:System.Windows.Forms.BindingSource> компонента.  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  Откройте файл MainWindow.xaml.  
  
5.  В режиме конструктора или XAML, выберите <xref:System.Windows.Window> элемент.  
  
6.  В окне «Свойства» щелкните **события** вкладки.  
  
7.  Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.  
  
8.  Скопируйте следующий код в <xref:System.Windows.FrameworkElement.Loaded> обработчика событий.  
  
     Этот код присваивает <xref:System.Windows.Forms.BindingSource> компонент в качестве контекста данных и заполняет `Customers` и `Orders` объекты адаптера.  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. Скопируйте следующий код в `MainWindow` определения класса.  
  
     Этот метод отвечает за <xref:System.Windows.Data.CollectionView.CurrentChanged> событий и обновляет текущий элемент привязки данных.  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Конструктор WPF](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Привязка данных в гибридных приложениях-пример](http://go.microsoft.com/fwlink/?LinkID=159983)  
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
