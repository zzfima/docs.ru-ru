---
title: Пошаговое руководство. Создание первого классического приложения WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3725e96b514b0204f10f6b5c45ed2bbec1d892de
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Пошаговое руководство. Создание первого классического приложения WPF
В этом пошаговом руководстве представляет собой введение в разработку [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] приложения, которое содержит элементы, которые являются общими для большинства [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложений: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметки, кода, определения приложения, элементы управления, макет, Привязка данных и стили. 
  
Пошаговом руководстве описывается разработка простого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения, выполнив следующие действия. 
  
-   Определение [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] на внешний вид приложения [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. 
  
-   Написание кода для создания модели поведения приложения. 
  
-   Создание управляющих определений приложения. 
  
-   Добавление элементов управления и создание макета, входящих в состав приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Создание стилей, обеспечивающих унифицированный внешний вид компонентов приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Привязка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с данными для заполнения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] из данных и синхронизации данных и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] синхронизированы. 
  
В конце данного пошагового руководства вы сможете создать автономный [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] приложение, которое позволяет пользователям просматривать отчеты о расходах для выбранных пользователей. Приложение будет состоять из нескольких [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] страницы, размещенные в окне обозревателя. 
  
Пример кода, который используется в этом пошаговом руководстве, доступен как для [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] и [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] в [введение в построение приложений WPF](http://go.microsoft.com/fwlink/?LinkID=160008). 

## <a name="prerequisites"></a>Предварительные требования  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)] или более поздняя версия

Дополнительные сведения об установке последней версии Visual Studio см. в разделе [установите Visual Studio](/visualstudio/install/install-visual-studio).
  
## <a name="creating-the-application-project"></a>Создание проекта приложения  
В этом разделе вы создадите инфраструктуру приложения, включающую в себя определение приложения, две страницы и изображение. 
  
1. Создайте проект приложения WPF на Visual Basic или Visual C# с именем `ExpenseIt`. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82). 
  
    > [!NOTE]
    >  В этом пошаговом руководстве используется <xref:System.Windows.Controls.DataGrid> управления, доступных в .NET Framework 4. Быть в том, что проект предназначен для .NET Framework 4 или более поздней версии. Дополнительные сведения см. в [практическом руководстве по настройке конкретной версии .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
2. Откройте файл Application.xaml (Visual Basic) или файл App.xaml (C#). 
  
     Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл определяет [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения и все его ресурсы. Этот файл также используется для указания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , будет автоматически отображаться при запуске приложения; в этом случае файл MainWindow.xaml. 
  
     Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     В C# он должен выглядеть следующим образом.  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. Откройте файл MainWindow.xaml. 
  
     Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл главного окна приложения, который отображает содержимое, созданное в страницах. <xref:System.Windows.Window> Класс определяет свойства окна, такие как заголовок, размер и значок и обрабатывает события, такие как открытие и закрытие окна. 
  
4. Изменение <xref:System.Windows.Window> элемент <xref:System.Windows.Navigation.NavigationWindow>. 
  
     Приложение будет переходить к различному содержимому согласно действиям пользователя. Поэтому главное <xref:System.Windows.Window> должно быть изменено <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> наследует все свойства <xref:System.Windows.Window>. <xref:System.Windows.Navigation.NavigationWindow> Элемент файла XAML создает экземпляр <xref:System.Windows.Navigation.NavigationWindow> класса. Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md). 
  
5. Измените следующие свойства на <xref:System.Windows.Navigation.NavigationWindow> элемента:  
  
    -   Задать <xref:System.Windows.Window.Title%2A> свойства «ExpenseIt». 
  
    -   Задать <xref:System.Windows.FrameworkElement.Width%2A> свойство до 500 пикселей. 
  
    -   Задать <xref:System.Windows.FrameworkElement.Height%2A> свойство до 350 пикселей. 
  
    -   Удалить <xref:System.Windows.Controls.Grid> элементов между <xref:System.Windows.Navigation.NavigationWindow> тегов. 
  
     Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     В C# он должен выглядеть следующим образом.  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. Откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs. 
  
     В этом файле кода программной части содержится код обработки событий, объявленных в файле MainWindow.xaml. Этот файл содержит разделяемый класс для окна, определенного в XAML-коде. 
  
7. Если вы используете C#, измените `MainWindow` являются производными от класса <xref:System.Windows.Navigation.NavigationWindow>. 
  
     В Visual Basic это выполняется автоматически при изменении окна в XAML-коде. 
  
     Код должен выглядеть следующим образом. 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a>Добавление файлов в приложение  
В этом разделе в приложение добавляются две страницы и изображение. 
  
1. Добавление новой страницы (WPF) в проект с именем `ExpenseItHome.xaml`. Дополнительные сведения см. в разделе [как: Добавление новых элементов в проект WPF](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad). 
  
     Эта страница отображается первой при запуске приложения. На ней выводится список, в котором можно выбрать человека и просмотреть отчет о его затратах. 
  
2. Откройте файл ExpenseItHome.xaml. 
  
3. Задать <xref:System.Windows.Controls.Page.Title%2A> для «ExpenseIt — Домашняя». 
  
     Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     А в C# он должен выглядеть следующим образом.  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. Откройте файл MainWindow.xaml. 
  
5. Задать <xref:System.Windows.Navigation.NavigationWindow.Source%2A> свойство <xref:System.Windows.Navigation.NavigationWindow> для «ExpenseItHome.xaml». 
  
     В результате ExpenseItHome.xaml будет первой страницей, открываемой при запуске приложения. Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     А в C# он должен выглядеть следующим образом.  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. Добавление новой страницы (WPF) в проект с именем `ExpenseReportPage.xaml`. 
  
     На этой странице будет выводиться отчет по расходам для человека, выбранного на странице ExpenseItHome.xaml. 
  
7. Откройте файл ExpenseReportPage.xaml. 
  
8. Задать <xref:System.Windows.Controls.Page.Title%2A> для «ExpenseIt — Просмотр расходов». 
  
     Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     А в C# он должен выглядеть следующим образом.  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. Откройте файлы ExpenseItHome.xaml.vb и ExpenseReportPage.xaml.vb (или ExpenseItHome.xaml.cs и ExpenseReportPage.xaml.cs). 
  
     При создании нового файла страницы Visual Studio автоматически создает файл кода программной части. Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя. 
  
     Код должен выглядеть следующим образом. 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. Добавьте изображение с именем *watermark.png* в проект. Можно создать собственное изображение или скопировать файл из образца кода. Дополнительные сведения см. в разделе [как: Добавление существующих элементов в проект](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)). 

## <a name="building-and-running-the-application"></a>Построение и запуск приложения  
В этом разделе выполняются сборка и запуск приложения. 
  
1. Построение и запуск приложения нажатием клавиши F5 или выбрав **начать отладку** из **отладки** меню. 
  
     На следующем рисунке показано приложение с <xref:System.Windows.Navigation.NavigationWindow> кнопки. 
  
     ![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2. Закройте приложение, чтобы вернуться к [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]. 
  
## <a name="creating-the-layout"></a>Создание макета  
Макет позволяет упорядочивать для размещения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов, а также управление размером и положением при [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] изменяется. Обычно макет создается с одним из следующих элементов управления макетом.  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
Каждый из этих элементов управления макетом поддерживает специальный тип макета дочерних элементов. Размер страниц приложения ExpenseIt может быть изменен. На каждой странице представлены элементы, которые упорядочены по горизонтали и вертикали рядом с другими элементами. Следовательно <xref:System.Windows.Controls.Grid> является идеальным элементом макета для приложения. 
  
> [!NOTE]
>  Дополнительные сведения о <xref:System.Windows.Controls.Panel> см [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md). Дополнительные сведения о макете см. в разделе [макета](../../../../docs/framework/wpf/advanced/layout.md). 
  
В разделе, создании одного столбца таблицы с тремя строками и 10 пикселей путем добавления определений столбцов и строк для <xref:System.Windows.Controls.Grid> в ExpenseItHome.xaml. 
  
1. Откройте файл ExpenseItHome.xaml. 
  
2. Задать <xref:System.Windows.FrameworkElement.Margin%2A> свойства <xref:System.Windows.Controls.Grid> элемента «10,0,10,10», который соответствует слева, сверху, справа и нижнего полей. 
  
3. Добавьте следующие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] между <xref:System.Windows.Controls.Grid> теги, чтобы создать определения строк и столбцов. 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     <xref:System.Windows.Controls.RowDefinition.Height%2A> Две строки имеет значение <xref:System.Windows.GridLength.Auto%2A> что означает, что строки будет изменяться размер основан на содержимое в строках. Значение по умолчанию <xref:System.Windows.Controls.RowDefinition.Height%2A> — <xref:System.Windows.GridUnitType.Star> изменения размера, это означает, что строки будут пропорционально изменяющегося доступного пространства. Например, если каждая из двух строк имеет высоту "*", высота каждой из них будет равна половине имеющегося свободного места.  
  
     Ваш <xref:System.Windows.Controls.Grid> должен выглядеть так, следующий код XAML:  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a>Добавление элементов управления  
В этом разделе, на домашней странице [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] обновляется для отображения списка людей, пользователи могут выбрать, чтобы отобразить отчет по расходам для выбранного пользователя из. Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением. Более подробную информацию см. в разделе [Элементы управления](../../../../docs/framework/wpf/controls/index.md). 
  
Для создания этого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ExpenseItHome.xaml добавляются следующие элементы:  
  
-   <xref:System.Windows.Controls.ListBox> (для список людей). 
  
-   <xref:System.Windows.Controls.Label> (для заголовков списка). 
  
-   <xref:System.Windows.Controls.Button> (чтобы щелкните, чтобы просмотреть отчет по расходам для человека, выбранного в списке). 
  
Каждый элемент управления помещается в строку <xref:System.Windows.Controls.Grid> , установив <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> вложенное свойство. Дополнительные сведения о вложенных свойствах см. в разделе [зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md). 
  
1. Откройте файл ExpenseItHome.xaml. 
  
2. Добавьте следующие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] между <xref:System.Windows.Controls.Grid> тегов. 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. Выполните сборку и запуск приложения. 
  
На следующем рисунке показаны элементы управления, созданные с помощью кода XAML в этом разделе. 
  
![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
## <a name="adding-an-image-and-a-title"></a>Добавление изображения и заголовка  
В этом разделе, на домашней странице [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] обновляется изображение и заголовок страницы. 
  
1. Откройте файл ExpenseItHome.xaml. 
  
2. Добавьте еще один столбец для <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> с фиксированным <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселей. 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. Добавьте строку в <xref:System.Windows.Controls.Grid.RowDefinitions%2A>. 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. Переместите элементы управления во второй столбец, задав <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> значение 1. Переместите каждый элемент управления в одну строку вниз, увеличив <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> на 1. 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. Задать <xref:System.Windows.Controls.Panel.Background%2A> из <xref:System.Windows.Controls.Grid> watermark.png файлом изображения. 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. Прежде чем <xref:System.Windows.Controls.Border>, добавьте <xref:System.Windows.Controls.Label> с содержимым «Просмотреть отчет о расходах» в заголовке страницы. 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. Выполните сборку и запуск приложения. 
  
На следующем рисунке показаны результаты действий из этого раздела. 
  
![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
## <a name="adding-code-to-handle-events"></a>Добавление кода для обработки событий  
  
1. Откройте файл ExpenseItHome.xaml. 
  
2. Добавить <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий <xref:System.Windows.Controls.Button> элемента. Дополнительные сведения см. в разделе [как: создание простого обработчика событий](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480). 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. Откройте файл ExpenseItHome.xaml.vb или ExpenseItHome.xaml.cs. 
  
4. Добавьте следующий код в <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий, который вызывает окно, чтобы перейти к файлу ExpenseReportPage.xaml. 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a>Создание пользовательского интерфейса для страницы ExpenseReportPage  
На странице ExpenseReportPage.xaml отображается отчет о расходах для человека, выбранного на странице ExpenseItHome.xaml. Добавляет элементы управления в этом разделе и создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для ExpenseReportPage.xaml. В этом разделе также добавляется фона и цвета заливки на разные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов. 
  
1. Откройте файл ExpenseReportPage.xaml. 
  
2. Добавьте следующий XAML-код между тегами <xref:System.Windows.Controls.Grid>. 
  
     Этот пользовательский Интерфейс аналогичен Интерфейсу, созданному в ExpenseItHome.xaml, за исключением того, данные отчета отображаются в <xref:System.Windows.Controls.DataGrid>. 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. Выполните сборку и запуск приложения. 
  
    > [!NOTE]
    >  Если вы получаете сообщение об <xref:System.Windows.Controls.DataGrid> не найден или не существует, убедитесь, что проект ориентирован на .NET Framework 4 или более поздней версии. Дополнительные сведения см. в [практическом руководстве по настройке конкретной версии .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
4. Нажмите кнопку **представление** кнопки. 
  
     Появится страница отчета по расходам. 
  
На следующем рисунке показана [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы, добавленные ExpenseReportPage.xaml. Обратите внимание на то, что кнопка возврата активна. 
  
![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
## <a name="styling-controls"></a>Настройка стиля элементов управления  
Внешний вид различных элементов часто могут совпадать для всех элементов одного типа в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] использует стили, чтобы варианты внешнего вида можно было многократно использовать для нескольких элементов. Повторное использование стилей помогает упростить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Создание и управление ими. Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md). В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями. 
  
1. Откройте файл Application.xaml или App.xaml. 
  
2. Добавьте следующий код XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> теги:  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] добавляет следующие стили:  
  
    -  `headerTextStyle`для форматирования заголовка страницы <xref:System.Windows.Controls.Label>; 
  
    -  `labelStyle`для форматирования элементов управления <xref:System.Windows.Controls.Label> ; 
  
    -  `columnHeaderStyle`для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>; 
  
    -  `listHeaderStyle`для форматирования элементов управления <xref:System.Windows.Controls.Border> заголовков списка; 
  
    -  `listHeaderTextStyle`Для форматирования заголовка списка <xref:System.Windows.Controls.Label>. 
  
    -  `buttonStyle`Для форматирования <xref:System.Windows.Controls.Button> на ExpenseItHome.xaml. 
  
     Обратите внимание, что стили, ресурсы и дочерних элементов <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> элемент свойства. Здесь стили применяются ко всем элементам в приложении. Пример использования ресурсов в [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] приложения, в разделе [использования ресурсов приложения](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md). 
  
3. Откройте файл ExpenseItHome.xaml. 
  
4. Замените весь код между <xref:System.Windows.Controls.Grid> элементы следующим кодом XAML. 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются. Например `headerTextStyle` применяется к «View Expense Report» <xref:System.Windows.Controls.Label>. 
  
5. Откройте файл ExpenseReportPage.xaml. 
  
6. Замените весь код между <xref:System.Windows.Controls.Grid> элементы следующим кодом XAML. 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     В элементы <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Border> будут добавлены стили. 
  
7. Выполните сборку и запуск приложения. 
  
     После добавления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в этом разделе приложение выглядит так же, как и перед обновлением с использованием стилей. 
  
## <a name="binding-data-to-a-control"></a>Привязка данных к элементу управления  
В этом разделе создайте [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] данные, привязанные к различным элементам управления. 
  
1. Откройте файл ExpenseItHome.xaml. 
  
2. После открывающего <xref:System.Windows.Controls.Grid> элемента, добавьте следующий код XAML для создания <xref:System.Windows.Data.XmlDataProvider> , содержащий данные для каждого пользователя. 
  
     Данные создаются в виде <xref:System.Windows.Controls.Grid> ресурсов. Обычно такие данные загружаются в виде файла, но для простоты в этом примере они добавляются в коде. 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. В <xref:System.Windows.Controls.Grid> ресурсов, добавьте следующий <xref:System.Windows.DataTemplate>, который определяет способ отображения данных в <xref:System.Windows.Controls.ListBox>. Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md). 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. Заменить существующий <xref:System.Windows.Controls.ListBox> следующим кодом XAML. 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     Этот код XAML привязывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> к источнику данных и применяет шаблон данных как <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>. 
  
## <a name="connecting-data-to-controls"></a>Подключение данных к элементам управления  
В этом разделе, можно написать код, который получает текущий элемент, выбранный в списке людей на странице ExpenseItHome.xaml и передается ссылка на конструктор `ExpenseReportPage` во время создания экземпляра. `ExpenseReportPage` задает контекст данных для переданного элемента, к которому будут привязаны элементы управления, определенные в файле ExpenseReportPage.xaml. 
  
1. Откройте файл ExpenseReportPage.xaml.vb или ExpenseReportPage.xaml.cs. 
  
2. Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека. 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. Откройте файл ExpenseItHome.xaml.vb или ExpenseItHome.xaml.cs. 
  
4. Изменение <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий для вызова нового конструктора, передавая данные отчета о затратах выбранного человека. 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a>Стили данных с помощью шаблонов данных  
В этом разделе обновления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для каждого элемента данных, привязанного к списков с помощью шаблонов данных. 
  
1. Откройте файл ExpenseReportPage.xaml. 
  
2. Привяжите содержимое «Name» и «Отдел» <xref:System.Windows.Controls.Label> свойство source элементов, соответствующих данных. Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md). 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. После открывающего <xref:System.Windows.Controls.Grid> элемента, добавьте следующие шаблоны данных, определяющие способ отображения данных отчета по расходам.  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. Применять шаблоны для <xref:System.Windows.Controls.DataGrid> столбцы, которые отображают расход данные отчета. 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. Выполните сборку и запуск приложения. 
  
6. Выберите человека и нажмите кнопку **представление** кнопки. 
  
 На рисунке ниже показаны обе страницы приложения ExpenseIt с элементами управления, макетом, стилями, привязкой данных и примененными шаблонами данных. 
  
 ![Снимки экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
## <a name="best-practices"></a>Рекомендации  
В этом примере демонстрируется конкретная функциональная возможность WPF, поэтому рекомендации по разработке приложений не соблюдаются. Полное описание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] лучшие методики разработки приложений, в следующих разделах соответствующим образом:  
  
-   Специальные возможности: [Рекомендации по специальным возможностям](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   Безопасность — [безопасности](../../../../docs/framework/wpf/security-wpf.md)  
  
-   Локализация: [Общие сведения о глобализации и локализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   Производительность [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
## <a name="whats-next"></a>Дальнейшие действия  
Теперь у вас есть несколько способов в вашем распоряжении для создания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с помощью [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Теперь вы получите более основательно изучить основные стандартные блоки, привязкой данных [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] приложения. Информация в этом разделе ни в коем случае не является исчерпывающей, но мы надеемся, что у вас также есть теперь некоторое представление о возможностях, которые вы можете изучить самостоятельно, помимо рассмотренных в этом разделе. 
  
 Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:  
  
-   [Архитектура WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [Макет](../../../../docs/framework/wpf/advanced/layout.md)  
  
 Более подробную информацию о создании приложений см. в следующих разделах:  
  
-   [Разработка приложения](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [Элементы управления](../../../../docs/framework/wpf/controls/index.md)  
  
-   [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Стили и шаблоны](../../../../docs/framework/wpf/controls/styles-and-templates.md)
