---
title: "Пошаговое руководство. Привязка к данным в гибридных приложениях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязка данных [взаимодействие с WPF]"
  - "гибридные приложения [взаимодействие с WPF]"
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# Пошаговое руководство. Привязка к данным в гибридных приложениях
Привязка источника данных к элементу управления необходима для предоставления пользователям доступа к базовым данным независимо от используемой системы — [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] или [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В данном пошаговом руководстве показано, как можно использовать привязку данных в гибридных приложениях, содержащих элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание проекта.  
  
-   Определение шаблона данных.  
  
-   Указание макета формы.  
  
-   Указание привязки данных.  
  
-   Отображение данных с помощью взаимодействия.  
  
-   Добавление источника данных к проекту.  
  
-   Привязка к источнику данных.  
  
 Полный пример кода для задач, приведенных в этом руководстве, см. в разделе [Пример привязки данных в гибридных приложениях](http://go.microsoft.com/fwlink/?LinkID=159983).  
  
 По окончании выполнения этих задач пользователь будет иметь представление о привязке данных в гибридных приложениях.  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Доступ к базе данных "Борей" на Microsoft SQL Server.  
  
## Создание проекта  
  
#### Чтобы создать и настроить проект  
  
1.  Создайте проект приложения WPF с именем `WPFWithWFAndDatabinding`.  
  
2.  В обозревателе решений добавьте ссылки на следующие сборки.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  В элементе <xref:System.Windows.Window> добавьте следующее сопоставление пространств имен [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Измените имя по умолчанию элемента <xref:System.Windows.Controls.Grid> на `mainGrid` путем задания свойства <xref:System.Windows.FrameworkElement.Name%2A>.  
  
     [!code-xml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## Определение шаблона данных.  
 Основной список клиентов отображается в элементе управления <xref:System.Windows.Controls.ListBox>.  В следующем примере кода определяется объект <xref:System.Windows.DataTemplate> с именем `ListItemsTemplate`, который управляет визуальным деревом элемента управления <xref:System.Windows.Controls.ListBox>.  Этот <xref:System.Windows.DataTemplate> присваивается свойству <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> элемента управления <xref:System.Windows.Controls.ListBox>.  
  
#### Чтобы определить шаблон данных  
  
-   Скопируйте следующую разметку XAML в объявление элемента <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## Задание макета формы.  
 Макет формы определяется таблицей из трех строк и трех столбцов.  Элементы управления <xref:System.Windows.Controls.Label> предоставляются для идентификации каждого столбца в таблице "Клиенты".  
  
#### Чтобы настроить макет таблицы  
  
-   Скопируйте следующую разметку XAML в объявление элемента <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### Чтобы настроить элементы управления Label  
  
-   Скопируйте следующую разметку XAML в объявление элемента <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## Задание привязки данных.  
 Основной список клиентов отображается в элементе управления <xref:System.Windows.Controls.ListBox>.  Вложенный `ListItemsTemplate` привязывает элемент управления <xref:System.Windows.Controls.TextBlock> к полю `ContactName` из базы данных.  
  
 Сведения о каждой записи клиента отображаются в нескольких элементах управления <xref:System.Windows.Controls.TextBox>.  
  
#### Чтобы задать привязку данных  
  
-   Скопируйте следующую разметку XAML в объявление элемента <xref:System.Windows.Controls.Grid>.  
  
     Класс <xref:System.Windows.Data.Binding> привязывает элемент управления <xref:System.Windows.Controls.TextBox> к соответствующим полям в базе данных.  
  
     [!code-xml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## Отображение данных с помощью взаимодействия.  
 Заказы, соответствующие выбранному клиенту, будут отображены в элементе управления <xref:System.Windows.Forms.DataGridView?displayProperty=fullName> с именем `dataGridView1`.  Элемент управления `dataGridView1` привязан к источнику данных в файле кода программной части.  Элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> является родительским для данного элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
#### Для отображения данных в элементе управления DataGridView  
  
-   Скопируйте следующую разметку XAML в объявление элемента <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## Добавление источника данных к проекту.  
 С помощью [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] можно легко добавить источник данных к проекту.  Данная процедура добавляет набор типобезопасных данных в проект.  Несколько других классов поддержки, таких как адаптеры таблиц для каждой из выбранных таблиц, также добавляются.  
  
#### Добавление источника данных  
  
1.  В меню **Данные** выберите команду **Добавить новый источник данных**.  
  
2.  В **мастере настройки источника данных** выберите подключение к базе данных Northwind с использованием набора данных.  Дополнительные сведения см. в разделе [Практическое руководство. Подключение к данным в базе данных](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md).  
  
3.  В ответ на запрос **Мастера настройки источника данных**, сохраните строку подключения как `NorthwindConnectionString`.  
  
4.  После вывода запроса на выбор объектов базы данных, выберите таблицы `Customers` и `Orders` и присвойте созданному набору данных имя `NorthwindDataSet`.  
  
## Привязка к источнику данных.  
 Компонент <xref:System.Windows.Forms.BindingSource?displayProperty=fullName> предоставляет унифицированный интерфейс для источника данных приложения.  Привязка к источнику данных реализуется в файле кода программной части.  
  
#### Чтобы выполнить привязку к источнику данных  
  
1.  Откройте файл кода программной части с именем MainWindow.xaml.vb или MainWindow.xaml.cs.  
  
2.  Скопируйте следующий код в определение класса `MainWindow`.  
  
     Этот код объявляет компонент <xref:System.Windows.Forms.BindingSource> и связанные вспомогательные классы, которые подключаются к базе данных.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  Скопируйте следующий код в конструктор.  
  
     Этот код создает и инициализирует компонент <xref:System.Windows.Forms.BindingSource>.  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  Откройте файл MainWindow.xaml.  
  
5.  В представлении конструирования или представлении XAML выберите элемент <xref:System.Windows.Window>.  
  
6.  В окне свойств перейдите на вкладку **События**.  
  
7.  Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.  
  
8.  Скопируйте следующий код в обработчик событий <xref:System.Windows.FrameworkElement.Loaded>.  
  
     Этот код назначает компонент <xref:System.Windows.Forms.BindingSource> в качестве контекста данных и заполняет объекты адаптера `Customers` и `Orders`.  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. Скопируйте следующий код в определение класса `MainWindow`.  
  
     Этот метод обрабатывает событие <xref:System.Windows.Data.CollectionView.CurrentChanged> и обновляет текущий элемент привязки данных.  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Нажмите клавишу F5 для построения и выполнения приложения.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Data Binding in Hybrid Applications Sample](http://go.microsoft.com/fwlink/?LinkID=159983)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)