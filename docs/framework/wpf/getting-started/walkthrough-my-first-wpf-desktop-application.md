---
title: "Пошаговое руководство. Начало работы с WPF | Microsoft Docs"
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
  - "начало работы, WPF"
  - "WPF, начало работы"
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 68
---
# Пошаговое руководство. Начало работы с WPF
<a name="introduction"></a> В этом пошаговом руководстве представлены общие сведения о разработке приложений [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], включающих в себя элементы, которые являются общими для большинства приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]: разметку [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], код программной части, определения приложения, элементы управления, макет, привязку данных и стили.  
  
 В этом пошаговом руководстве описывается разработка простого приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   Определение [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-кода для разработки [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] приложения.  
  
-   Написание кода для построения модели поведения приложения.  
  
-   Создание управляющих определений приложения.  
  
-   Добавление элементов управления и создание макета, входящих в состав [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения.  
  
-   Создание стилей, обеспечивающих унифицированный внешний вид компонентов приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   Связывание [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с данными для заполнения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] из данных и синхронизации данных с [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Изучив данное пошаговое руководство, вы сможете создать автономное приложение [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], которое позволит пользователям просматривать отчеты о расходах выбранных лиц.  Приложение будет состоять из нескольких страниц [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], размещенных в окне, напоминающем браузер.  
  
 Пример кода, который используется в этом пошаговом руководстве, доступен как для [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)], так и для [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]; см. раздел [Введение в разработку приложений WPF](http://go.microsoft.com/fwlink/?LinkID=160008).  
  
<a name="Requirements"></a>   
## Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]  
  
 Дополнительные сведения об установке [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] см. в разделе [Установка Visual Studio](../Topic/Install%20Visual%20Studio%202015.md).  
  
<a name="Create_The_Application_Code_Files"></a>   
## Создание проекта приложения  
 В этом разделе создается инфраструктура приложения, включающая определение приложения, две страницы и изображение.  
  
1.  Создайте новый проект приложения WPF на языке Visual Basic или Visual C\# с именем `ExpenseIt`.  Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/ru-ru/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
    > [!NOTE]
    >  В этом пошаговом руководстве используется элемент управления <xref:System.Windows.Controls.DataGrid>, доступных в платформе .NET Framework 4.  Необходимо, чтобы проект предназначался для платформы .NET Framework 4.  Дополнительные сведения см. в разделе [Практическое руководство. Определение целевой версии .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
2.  Откройте файл Application.xaml \(Visual Basic\) или App.xaml \(C\#\).  
  
     Этот файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] определяет приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и все его ресурсы. Данный файл также используется для указания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], автоматически отображаемого при запуске приложения \(в данном случае — MainWindow.xaml\).  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-код должен выглядеть следующим образом в Visual Basic:  
  
     [!code-xml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     А в C\# он должен выглядеть следующим образом:  
  
     [!code-xml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3.  Откройте файл MainWindow.xaml.  
  
     Этот [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-файл представляет главное окно приложения, в котором отображается созданное содержимое страниц.  Класс <xref:System.Windows.Window> определяет свойства окна, такие как заголовок, размер и значок, и обрабатывает события, такие как открытие и закрытие окна.  
  
4.  Замените элемент <xref:System.Windows.Window> на <xref:System.Windows.Navigation.NavigationWindow>.  
  
     Приложение будет переходить к различному содержимому согласно действиям пользователя.  Поэтому главное окно <xref:System.Windows.Window> необходимо изменить на <xref:System.Windows.Navigation.NavigationWindow>.  Класс <xref:System.Windows.Navigation.NavigationWindow> наследует все свойства класса <xref:System.Windows.Window>.  Элемент <xref:System.Windows.Navigation.NavigationWindow> в XAML\-файле создает экземпляр класса <xref:System.Windows.Navigation.NavigationWindow>.  Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
5.  Измените следующие свойства элемента <xref:System.Windows.Navigation.NavigationWindow>.  
  
    -   Задайте свойству <xref:System.Windows.Window.Title%2A> значение "ExpenseIt".  
  
    -   Задайте свойству <xref:System.Windows.FrameworkElement.Width%2A> значение 500 пикселей.  
  
    -   Задайте свойству <xref:System.Windows.FrameworkElement.Height%2A> значение 350 пикселей.  
  
    -   Удалите элементы <xref:System.Windows.Controls.Grid> между тегами <xref:System.Windows.Navigation.NavigationWindow>.  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-код должен выглядеть следующим образом в Visual Basic:  
  
     [!code-xml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     А в C\# он должен выглядеть следующим образом:  
  
     [!code-xml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6.  Откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs.  
  
     В этом файле кода программной части содержится код обработки событий, объявленных в файле MainWindow.xaml.  В этом файле содержится разделяемый класс окна, определенного в XAML\-коде.  
  
7.  Если используется язык C\#, измените класс `MainWindow` так, чтобы он наследовался от класса <xref:System.Windows.Navigation.NavigationWindow>.  
  
     В языке Visual Basic это выполняется автоматически при изменении окна в XAML\-коде.  
  
     Код должен выглядеть следующим образом.  
  
     [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
     [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
<a name="add_files_to_the_application"></a>   
## Добавление файлов в приложение  
 В этом разделе в приложение добавляются две страницы и изображение.  
  
1.  Добавьте в проект новую страницу \(WPF\) с именем `ExpenseItHome.xaml`.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление новых элементов в проекте WPF](http://msdn.microsoft.com/ru-ru/17e6b238-fc32-4385-98ef-2f66ca09d9ad).  
  
     Эта страница отображается первой при запуске приложения.  На ней выводится список, в котором можно выбрать человека и просмотреть отчет о его затратах.  
  
2.  Откройте файл ExpenseItHome.xaml.  
  
3.  Задайте свойству <xref:System.Windows.Controls.Page.Title%2A> значение "ExpenseIt \- Home".  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-код должен выглядеть следующим образом в Visual Basic:  
  
     [!code-xml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     А в C\# он должен выглядеть следующим образом:  
  
     [!code-xml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4.  Откройте файл MainWindow.xaml.  
  
5.  Задайте свойству <xref:System.Windows.Navigation.NavigationWindow.Source%2A> объекта <xref:System.Windows.Navigation.NavigationWindow> значение "ExpenseItHome.xaml".  
  
     В результате ExpenseItHome.xaml будет первой страницей, открываемой при запуске приложения.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-код должен выглядеть следующим образом в Visual Basic:  
  
     [!code-xml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     А в C\# он должен выглядеть следующим образом:  
  
     [!code-xml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6.  Добавьте в проект новую страницу \(WPF\) с именем `ExpenseReportPage.xaml`.  
  
     На этой странице будет представлен отчет о расходах для человека, выбранного на странице ExpenseItHome.xaml.  
  
7.  Откройте файл ExpenseReportPage.xaml.  
  
8.  Задайте свойству <xref:System.Windows.Controls.Page.Title%2A> значение "ExpenseIt \- View Expense".  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-код должен выглядеть следующим образом в Visual Basic:  
  
     [!code-xml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     А в C\# он должен выглядеть следующим образом:  
  
     [!code-xml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. Откройте файлы ExpenseItHome.xaml.vb и ExpenseReportPage.xaml.vb \(или ExpenseItHome.xaml.cs и ExpenseReportPage.xaml.cs\).  
  
     При создании нового файла страницы Visual Studio автоматически создает файл кода программной части.  Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.  
  
     Код должен выглядеть следующим образом.  
  
     [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
     [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
     [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
     [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. Добавьте в проект изображение с именем watermark.png.  Можно создать собственное изображение или скопировать файл из образца кода.  Дополнительные сведения см. в разделе [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/ru-ru/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
<a name="Build_The_Application"></a>   
## Построение и запуск приложения  
 В этом разделе выполняется построение и запуск приложения.  
  
1.  Выполните построение и запуск приложения, воспользовавшись клавишей F5 или выбрав пункт **Начать отладку** в меню **Отладка**.  
  
     На следующем рисунке показано приложение с кнопками окна <xref:System.Windows.Navigation.NavigationWindow>.  
  
     ![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2.  Закройте приложение и вернитесь в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
<a name="Add_Layout"></a>   
## Создание макета  
 Макет обеспечивает упорядоченное расположение элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], а также управление их размером и положением при изменении размера [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Обычно макет создается с одним из следующих элементов управления макетом:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 Для каждого из этих элементов управления макетом поддерживается специальный тип макета дочерних элементов.  Размер страниц приложения ExpenseIt может быть изменен. На каждой странице представлены элементы, которые упорядочены по горизонтали и вертикали рядом с другими элементами.  Следовательно, <xref:System.Windows.Controls.Grid> является идеальным элементом макета для приложения.  
  
> [!NOTE]
>  Дополнительные сведения об элементах <xref:System.Windows.Controls.Panel> см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).  Дополнительные сведения о макете см. в разделе [Макет](../../../../docs/framework/wpf/advanced/layout.md).  
  
 В этом разделе создается таблица с одним столбцом, тремя строками и полями шириной 10 пикселей путем добавления определений столбцов и строк в класс <xref:System.Windows.Controls.Grid> в файле ExpenseItHome.xaml.  
  
1.  Откройте файл ExpenseItHome.xaml.  
  
2.  Задайте свойству <xref:System.Windows.FrameworkElement.Margin%2A> элемента <xref:System.Windows.Controls.Grid> значение "10,0,10,10", указывающее ширину полей слева, сверху, справа и снизу соответственно.  
  
3.  Добавьте следующий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-код между тегами <xref:System.Windows.Controls.Grid>, чтобы создать определения строк и столбцов.  
  
     [!code-xml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     Свойству двух столбцов <xref:System.Windows.Controls.RowDefinition.Height%2A> задано значение <xref:System.Windows.GridLength.Auto%2A>, что означает, что размер строк будет зависеть от их содержимого.  По умолчанию свойство <xref:System.Windows.Controls.RowDefinition.Height%2A> имеет размер <xref:System.Windows.GridUnitType>, что означает, что в качестве размера строки задается пропорциональная часть свободного места.  Например, если каждая из двух строк имеет высоту "\*", высота каждой из них будет равна половине имеющегося свободного места.  
  
     Класс <xref:System.Windows.Controls.Grid> должен быть подобен следующему XAML\-коду.  
  
     [!code-xml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
<a name="Add_Controls"></a>   
## Добавление элементов управления  
 В этом разделе обновляется [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] домашней страницы: теперь на ней отображается список лиц, для которых можно вывести отчеты о расходах.  Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.  Дополнительные сведения см. в разделе [Элементы управления](../../../../docs/framework/wpf/controls/index.md).  
  
 Чтобы создать этот [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], в файл ExpenseItHome.xaml необходимо добавить следующие элементы.  
  
-   <xref:System.Windows.Controls.ListBox> — отображение списка людей.  
  
-   <xref:System.Windows.Controls.Label> — заголовок списка.  
  
-   <xref:System.Windows.Controls.Button> — кнопка для просмотра отчета о расходах для выбранного в списке человека.  
  
 Каждый элемент управления необходимо поместить в строку таблицы <xref:System.Windows.Controls.Grid>, указав вложенное свойство <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=fullName>.  Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
1.  Откройте файл ExpenseItHome.xaml.  
  
2.  Добавьте следующий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-код между тегами <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3.  Постройте и запустите приложение.  
  
 На следующем рисунке показаны элементы управления, созданные с помощью XAML\-кода в этом разделе.  
  
 ![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
<a name="Add_an_Image"></a>   
## Добавление изображения и заголовка  
 В этом разделе обновляется [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] домашней страницы: на нее добавляется изображение и заголовок страницы.  
  
1.  Откройте файл ExpenseItHome.xaml.  
  
2.  Добавьте столбец в свойство <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> с фиксированной длиной <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселей.  
  
     [!code-xml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3.  Добавьте строку в свойство <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.  
  
     [!code-xml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4.  Переместите элементы управления во второй столбец, задав свойству <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=fullName> значение 1.  Переместите каждый элемент управления на одну строку вниз, увеличив значение свойства <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=fullName> на 1.  
  
     [!code-xml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5.  В качестве значения свойства <xref:System.Windows.Controls.Panel.Background%2A> класса <xref:System.Windows.Controls.Grid> задайте файл изображения watermark.png.  
  
     [!code-xml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6.  В заголовке страницы перед элементом <xref:System.Windows.Controls.Border> добавьте элемент <xref:System.Windows.Controls.Label> с содержимым "View Expense Report".  
  
     [!code-xml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7.  Постройте и запустите приложение.  
  
 На следующем рисунке показаны результаты действий из этого раздела.  
  
 ![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
<a name="Add_Code_to_Process_Events"></a>   
## Добавление кода для обработки событий  
  
1.  Откройте файл ExpenseItHome.xaml.  
  
2.  Добавьте обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в элемент <xref:System.Windows.Controls.Button>.  Дополнительные сведения см. в разделе [Практическое руководство. Создание простого обработчика событий](http://msdn.microsoft.com/ru-ru/b1456e07-9dec-4354-99cf-18666b64f480).  
  
     [!code-xml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3.  Откройте файл ExpenseItHome.xaml.vb или ExpenseItHome.xaml.cs.  
  
4.  Добавьте в обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> следующий код, обеспечивающий переход окна к файлу ExpenseReportPage.xaml.  
  
     [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
     [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
<a name="Create_the_UI_for_Pane2"></a>   
## Создание пользовательского интерфейса для страницы ExpenseReportPage  
 На странице ExpenseReportPage.xaml отображается отчет о расходах для человека, выбранного на странице ExpenseItHome.xaml.  В этом разделе на страницу ExpenseReportPage.xaml добавляются элементы управления, и для нее создается [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  На нее также добавляется фон и цвета заливки для различных элементов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
1.  Откройте файл ExpenseReportPage.xaml.  
  
2.  Добавьте следующий XAML\-код между тегами <xref:System.Windows.Controls.Grid>.  
  
     Этот пользовательский интерфейс аналогичен пользовательскому интерфейсу, созданному в файле ExpenseItHome.xaml, за исключением того, что данные отчета отображаются в элементе управления <xref:System.Windows.Controls.DataGrid>.  
  
     [!code-xml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3.  Постройте и запустите приложение.  
  
    > [!NOTE]
    >  При появлении сообщения об ошибке, указывающего, что элемент управления <xref:System.Windows.Controls.DataGrid> не найден или не существует, убедитесь, что проект предназначен для платформы .NET Framework 4.  Дополнительные сведения см. в разделе [Практическое руководство. Определение целевой версии .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
4.  Нажмите кнопку **View** \(Просмотреть\).  
  
     Отобразится отчет о затратах.  
  
 На следующем рисунке показаны элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], добавленные на страницу ExpenseReportPage.xaml.  Обратите внимание, что доступна кнопка "назад".  
  
 ![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
<a name="Add_Code_to_Style_a_Control"></a>   
## Цвета стилей  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] часто подразумевает одинаковый внешний вид различных элементов для всех элементов одного типа.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] использует стили, чтобы варианты внешнего вида можно было многократно использовать для нескольких элементов.  Повторное использование стилей помогает упростить создание [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-кода и управление им.  За дополнительными сведениями о стилях обратитесь к разделу [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.  
  
1.  Откройте файл Application.xaml или App.xaml.  
  
2.  Добавьте следующий XAML\-код между тегами <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>.  
  
     [!code-xml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     В этом [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-коде добавляются следующие стили.  
  
    -   `headerTextStyle` — форматирование заголовка страницы <xref:System.Windows.Controls.Label>.  
  
    -   `labelStyle` — форматирование элементов управления <xref:System.Windows.Controls.Label>.  
  
    -   `columnHeaderStyle` — форматирование <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
    -   `listHeaderStyle` — форматирование элементов управления заголовка списка <xref:System.Windows.Controls.Border>.  
  
    -   `listHeaderTextStyle` — форматирование заголовка списка <xref:System.Windows.Controls.Label>.  
  
    -   `buttonStyle` — форматирование элемента <xref:System.Windows.Controls.Button> в файле ExpenseItHome.xaml.  
  
     Обратите внимание, что стили представляют собой ресурсы и являются дочерними элементами свойства <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>.  Здесь стили применяются ко всем элементам в приложении.  Пример использования ресурсов в приложении [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] см. в разделе [Использование ресурсов приложения](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).  
  
3.  Откройте файл ExpenseItHome.xaml.  
  
4.  Замените все содержимое между элементами <xref:System.Windows.Controls.Grid> следующим XAML\-кодом.  
  
     [!code-xml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     Свойства, определяющие внешний вид элементов управления \(такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily>\), удаляются, и вместо них применяются стили.  Например, стиль `headerTextStyle` применяется к тексту "View Expense Report" \(элемент <xref:System.Windows.Controls.Label>\).  
  
5.  Откройте файл ExpenseReportPage.xaml.  
  
6.  Замените все содержимое между элементами <xref:System.Windows.Controls.Grid> следующим XAML\-кодом.  
  
     [!code-xml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     Таким образом, в элементы <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Border> будут добавлены стили.  
  
7.  Постройте и запустите приложение.  
  
     После добавления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-кода в этом разделе приложение выглядит так же, как и перед обновлением с использованием стилей.  
  
<a name="Bind_Data_to_a_Control"></a>   
## Привязка данных к элементу управления  
 В этом разделе создаются [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-данные, привязанные к различным элементам управления.  
  
1.  Откройте файл ExpenseItHome.xaml.  
  
2.  Открыв элемент <xref:System.Windows.Controls.Grid>, добавьте следующий XAML\-код для создания объекта <xref:System.Windows.Data.XmlDataProvider>, содержащего данные по каждому человеку.  
  
     Данные создаются в качестве ресурса объекта <xref:System.Windows.Controls.Grid>.  Обычно такие ресурсы загружаются в виде файла, но в данном случае данные добавлены в код для простоты.  
  
     [!code-xml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3.  В ресурсе <xref:System.Windows.Controls.Grid> добавьте следующий элемент <xref:System.Windows.DataTemplate>, определяющий способ отображения данных в списке <xref:System.Windows.Controls.ListBox>.  Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
     [!code-xml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4.  Замените существующий класс <xref:System.Windows.Controls.ListBox> следующим XAML\-кодом.  
  
     [!code-xml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     Этот XAML\-код обеспечивает привязку свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> элемента <xref:System.Windows.Controls.ListBox> к источнику данных и применяет шаблон источника данных как элемент <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.  
  
<a name="Connect_Data_to_Controls"></a>   
## Подключение данных к элементам управления  
 В этом разделе записывается код, извлекающий текущий пункт, выбранный в списке людей на странице ExpenseItHome.xaml, и передающий его ссылку конструктору элемента `ExpenseReportPage` во время создания объекта.  `ExpenseReportPage` задает контекст данных для переданного элемента, к которому будут привязаны элементы управления, определенные в файле ExpenseReportPage.xaml.  
  
1.  Откройте файл ExpenseReportPage.xaml.vb или ExpenseReportPage.xaml.cs.  
  
2.  Добавьте конструктор, принимающий объект, чтобы можно было передать данные отчета о затратах выбранного человека.  
  
     [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
     [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3.  Откройте файл ExpenseItHome.xaml.vb или ExpenseItHome.xaml.cs.  
  
4.  Измените обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> так, чтобы он вызывал новый конструктор и передавал ему данные отчета о затратах выбранного человека.  
  
     [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
     [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
<a name="Add_Style_to_Data"></a>   
## Стилизация данных с помощью шаблонов данных  
 В этом разделе обновляется [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] каждого элемента в списках с привязкой данных с помощью шаблонов данных.  
  
1.  Откройте файл ExpenseReportPage.xaml.  
  
2.  Привяжите содержимое "Name" и "Department" элементов <xref:System.Windows.Controls.Label> к соответствующему свойству источника данных.  Дополнительные сведения о привязке данных см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     [!code-xml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3.  После открывающего элемента <xref:System.Windows.Controls.Grid> добавьте следующие шаблоны данных, определяющие способ отображения отчета о затратах.  
  
     [!code-xml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4.  Примените шаблоны к столбцам <xref:System.Windows.Controls.DataGrid>, в которых отображаются данные отчета о затратах.  
  
     [!code-xml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5.  Постройте и запустите приложение.  
  
6.  Выберите человека и нажмите кнопку **View** \(Просмотреть\).  
  
 На следующем рисунке представлены обе страницы приложения ExpenseIt, к которым применены элементы управления, макет, стили, привязка данных и шаблоны данных.  
  
 ![Снимки экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
<a name="Best_Practices"></a>   
## Рекомендации  
 В этом примере демонстрируется конкретная функциональная возможность WPF, поэтому рекомендации по разработке приложений не соблюдаются.  Подробные рекомендации по разработке приложений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] см. в следующих разделах.  
  
-   Специальные возможности: [Рекомендации по специальным возможностям](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   Безопасность: [Безопасность](../../../../docs/framework/wpf/security-wpf.md)  
  
-   Локализация: [Общие сведения о глобализации и локализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   Производительность: [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
<a name="Whats_Next"></a>   
## Что дальше?  
 Теперь вы ознакомились с различными способами создания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с использованием [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Далее следует более основательно изучить основные конструктивные блоки приложений [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] с привязкой к данным.  Целью этого раздела не являлось углубленное изучение, однако вы получили общие сведения, которые могут использоваться в качестве базы для самостоятельного изучения возможностей, не освещенных в этом разделе.  
  
 Дополнительные сведения об архитектуре и моделях программирования WPF см. в следующих разделах.  
  
-   [Архитектура WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [Макет](../../../../docs/framework/wpf/advanced/layout.md)  
  
 Подробные сведения о создании приложений см. в следующих разделах.  
  
-   [Разработка приложений](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [Элементы управления](../../../../docs/framework/wpf/controls/index.md)  
  
-   [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## См. также  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Стили и шаблоны](../../../../docs/framework/wpf/controls/styles-and-templates.md)