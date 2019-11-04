---
title: Руководство. Создание первого приложения WPF в Visual Studio 2019 — .NET Framework
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: vs-dotnet
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d45932f6a8822ec2aaa40cd52431d9981ab8fa1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453759"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Руководство. Создание первого приложения WPF в Visual Studio 2019

В этой статье показано, как разработать классическое приложение Windows Presentation Foundation (WPF), включающее элементы, которые являются общими для большинства приложений WPF: разметка XAML (XAML), код программной части, определения приложений, элементы управления, макет, привязка данных и стили. Для разработки приложения вы будете использовать Visual Studio. 

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
>
> - Создайте проект WPF.
> - Используйте XAML для проектирования внешнего вида пользовательского интерфейса приложения.
> - Напишите код для создания поведения приложения.
> - Создайте определение приложения для управления приложением.
> - Добавьте элементы управления и создайте макет, чтобы составить пользовательский интерфейс приложения.
> - Создание стилей для согласованного внешнего вида в пользовательском интерфейсе приложения.
> - Привязка пользовательского интерфейса к данным для заполнения пользовательского интерфейса данными и синхронизации данных и пользовательского интерфейса.

По завершении работы с этим руководством вы создадите автономное приложение Windows, которое позволит пользователям просматривать отчеты о расходах для выбранных лиц. Приложение состоит из нескольких страниц WPF, размещенных в окне в стиле браузера.

> [!TIP]
> Пример кода, используемый в этом руководстве, доступен как для Visual Basic, так и C# в [руководстве по примерам кода приложения WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).
>
> Язык кода образца кода можно переключать между C# и Visual Basic с помощью селектора языка в верхней части этой страницы.

## <a name="prerequisites"></a>Необходимые компоненты

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой " **Разработка классических приложений .NET** ".

   Дополнительные сведения об установке последней версии Visual Studio см. в [статье Установка Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Создание проекта приложения

Первым шагом является создание инфраструктуры приложения, включающей определение приложения, две страницы и изображение.

1. Создайте новый проект приложения WPF в Visual Basic или Visual C# с именем **`ExpenseIt`** :

   1. Откройте Visual Studio и выберите **создать новый проект** в меню **Приступая к работе** .

      Откроется диалоговое окно **Создание нового проекта** .

   2. В раскрывающемся списке **язык** выберите либо **C#** или **Visual Basic**.
      
   3. Выберите шаблон **приложения WPF (.NET Framework)** и нажмите кнопку **Далее**. 
     
      ![Диалоговое окно создания нового проекта](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      Откроется диалоговое окно **Настройка нового проекта** .

   4. Введите имя проекта **`ExpenseIt`** а затем щелкните **создать**.

      ![Диалоговое окно "Настройка нового проекта"](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio создаст проект и откроет конструктор для окна приложения по умолчанию с именем **MainWindow. XAML**.

2. Откройте *Application. XAML* (Visual Basic) или *app. XAML* (C#).

    Этот XAML-файл определяет приложение WPF и все ресурсы приложения. Этот файл также используется для указания пользовательского интерфейса, в данном случае *MainWindow. XAML*, который автоматически отображается при запуске приложения.

    КОД XAML должен выглядеть следующим образом в Visual Basic:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    И следующим образом C#:

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Откройте файл *MainWindow. XAML*.

    Этот XAML-файл является главным окном приложения и отображает содержимое, созданное на страницах. Класс <xref:System.Windows.Window> определяет свойства окна, такие как заголовок, размер или значок, а также обрабатывает события, такие как закрытие или скрытие.

4. Измените элемент <xref:System.Windows.Window> на <xref:System.Windows.Navigation.NavigationWindow>, как показано в следующем коде XAML:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Это приложение переходит к другому содержимому в зависимости от введенных пользователем данных. Именно поэтому основное <xref:System.Windows.Window> необходимо изменить на <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> наследует все свойства <xref:System.Windows.Window>. Элемент <xref:System.Windows.Navigation.NavigationWindow> в файле XAML создает экземпляр класса <xref:System.Windows.Navigation.NavigationWindow>. Дополнительные сведения см. в разделе [Общие сведения о навигации](../app-development/navigation-overview.md).

5. Удалите элементы <xref:System.Windows.Controls.Grid> из тегов <xref:System.Windows.Navigation.NavigationWindow>.

6. Измените следующие свойства в коде XAML для элемента <xref:System.Windows.Navigation.NavigationWindow>:

    - Задайте для свойства <xref:System.Windows.Window.Title%2A> значение "`ExpenseIt`".

    - Задайте для свойства <xref:System.Windows.FrameworkElement.Height%2A> значение 350 пикселей.

    - Задайте для свойства <xref:System.Windows.FrameworkElement.Width%2A> значение 500 пикселей.

    КОД XAML должен выглядеть следующим образом для Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    И следующим образом C#:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Откройте файл *MainWindow. XAML. vb* или *MainWindow.XAML.CS*.

    Этот файл является файлом кода программной части, который содержит код для работы с событиями, объявленными в файле *MainWindow. XAML*. Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.

8. Если вы используете C#, измените класс `MainWindow` на производный от <xref:System.Windows.Navigation.NavigationWindow>. (В Visual Basic это происходит автоматически при изменении окна в XAML.) Теперь C# ваш код должен выглядеть следующим образом:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Добавление файлов в приложение

В этом разделе вы добавите в приложение две страницы и изображение.

1. Добавьте в проект новую страницу и назовите ее *`ExpenseItHome.xaml`* :

   1. В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта **`ExpenseIt`** и выберите пункт **добавить** > **страницу**.

   1. В диалоговом окне **Добавление нового элемента** шаблон **Page (WPF)** уже выбран. Введите имя **`ExpenseItHome`** и нажмите кнопку **Добавить**.

    Эта страница является первой страницей, отображаемой при запуске приложения. Отобразится список людей для выбора, чтобы отобразить отчет о расходах для.

1. Откройте *`ExpenseItHome.xaml`* .

1. Задайте для <xref:System.Windows.Controls.Page.Title%2A> значение "`ExpenseIt - Home`".

1. Задайте для `DesignHeight` значение 350 пикселей, а `DesignWidth` — 500 пикселей.

    Теперь XAML выглядит следующим образом для Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    И следующим образом C#:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Откройте файл *MainWindow. XAML*.

1. Добавьте свойство <xref:System.Windows.Navigation.NavigationWindow.Source%2A> в элемент <xref:System.Windows.Navigation.NavigationWindow> и задайте для него значение "`ExpenseItHome.xaml`".

    Этот параметр задает *`ExpenseItHome.xaml`* первой страницей, открытой при запуске приложения. 

    Пример XAML в Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    И в C#:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > Также можно задать свойство **Source** в категории **Разное** в окне **Свойства** .
   >
   > ![Свойство Source в окно свойств](./media/properties-source.png)

1. Добавьте еще одну новую страницу WPF в проект и назовите ее *файл ExpenseReportPage. XAML*::

   1. В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта **`ExpenseIt`** и выберите пункт **добавить** > **страницу**.

   1. В диалоговом окне **Добавление нового элемента** выберите шаблон **Page (WPF)** . Введите имя **файл ExpenseReportPage**и нажмите кнопку **Добавить**.

    На этой странице отображается отчет о расходах для пользователя, выбранного на странице **`ExpenseItHome`** .

1. Откройте файл *ExpenseReportPage.xaml*.

1. Задайте для <xref:System.Windows.Controls.Page.Title%2A> значение "`ExpenseIt - View Expense`".

1. Задайте для `DesignHeight` значение 350 пикселей, а `DesignWidth` — 500 пикселей. 

    *Файл ExpenseReportPage. XAML* теперь выглядит следующим образом в Visual Basic:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    И следующим образом C#:

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Откройте *ExpenseItHome. XAML. vb* и *файл ExpenseReportPage. XAML. vb*, а также *ExpenseItHome.XAML.CS* и *ExpenseReportPage.XAML.CS*.

    При создании нового файла подкачки Visual Studio автоматически создает свой файл *кода программной части* . Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.

    Код должен выглядеть следующим образом для **`ExpenseItHome`** :

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    И, как и для **файл ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Добавьте в проект образ с именем *водяной знак. png* . Вы можете создать собственный образ, скопировать файл из примера кода или получить его из репозитория GitHub [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .

    1. Щелкните правой кнопкой мыши узел проекта и выберите **добавить** > **существующий элемент**или нажмите **SHIFT**+**ALT**+**A**.

    2. В диалоговом окне **Добавление существующего элемента** задайте для фильтра файлов значение **все файлы** или **файлы изображений**, перейдите к файлу изображения, который необходимо использовать, а затем нажмите кнопку **Добавить**.

## <a name="build-and-run-the-application"></a>Построение и запуск приложения

1. Чтобы выполнить сборку и запуск приложения, нажмите клавишу **F5** или выберите **начать отладку** в меню **Отладка** .

    На следующем рисунке показано приложение с кнопками <xref:System.Windows.Navigation.NavigationWindow>.

    ![После сборки и запуска приложения.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Закройте приложение, чтобы вернуться в Visual Studio.

## <a name="create-the-layout"></a>Создание макета

Макет предоставляет упорядоченный способ размещения элементов пользовательского интерфейса, а также управляет размером и положением этих элементов при изменении размера пользовательского интерфейса. Обычно макет создается с одним из следующих элементов управления макетом.

- <xref:System.Windows.Controls.Canvas> — определяет область, в которой можно явно располагать дочерние элементы с помощью координат, относящихся к области Canvas.
- <xref:System.Windows.Controls.DockPanel> — определяет область, в которой можно расположить дочерние элементы по горизонтали или по вертикали относительно друг друга.
- <xref:System.Windows.Controls.Grid> — определяет гибкую область сетки, состоящую из столбцов и строк.
- <xref:System.Windows.Controls.StackPanel> — упорядочивает дочерние элементы в одну строку, которая может быть ориентирована горизонтально или вертикально.
- <xref:System.Windows.Controls.VirtualizingStackPanel> — упорядочивает и виртуализировать содержимое в одной строке, ориентированной либо горизонтально, либо вертикально.
- <xref:System.Windows.Controls.WrapPanel> размещает дочерние элементы в последовательном положении слева направо, разбивая содержимое на следующую строку на границе содержащего поля. Последующее упорядочение происходит последовательно сверху вниз или справа налево в зависимости от значения свойства Orientation.

Каждый из этих элементов управления макета поддерживает определенный тип макета для своих дочерних элементов. размеры страниц `ExpenseIt` можно изменять, и каждая страница содержит элементы, расположенные горизонтально и вертикально вместе с другими элементами. В этом примере <xref:System.Windows.Controls.Grid> используется в качестве элемента макета для приложения.

> [!TIP]
> Дополнительные сведения об элементах <xref:System.Windows.Controls.Panel> см. в разделе [Общие сведения о панелях](../controls/panels-overview.md). Дополнительные сведения о макете см. в разделе [Layout](../advanced/layout.md).

В этом разделе вы создадите таблицу с одним столбцом с тремя строками и 10-пиксельным полем, добавив определения столбцов и строк в <xref:System.Windows.Controls.Grid> в *`ExpenseItHome.xaml`* .

1. В *`ExpenseItHome.xaml`* задайте для свойства <xref:System.Windows.FrameworkElement.Margin%2A> элемента <xref:System.Windows.Controls.Grid> значение "10, 0, 10, 10", которое соответствует левому, верхнему, правому и нижнему полям:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > Можно также задать значения **полей** в окне **свойства** в категории **Макет** :
   >
   > ![Значения полей в окно свойств](./media/properties-margin.png)

2. Добавьте следующий код XAML между тегами <xref:System.Windows.Controls.Grid>, чтобы создать определения строк и столбцов:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <xref:System.Windows.Controls.RowDefinition.Height%2A> двух строк имеет значение <xref:System.Windows.GridLength.Auto%2A>. Это означает, что размер строк зависит от содержимого строк. <xref:System.Windows.Controls.RowDefinition.Height%2A> по умолчанию — <xref:System.Windows.GridUnitType.Star> размер, что означает, что высота строки является взвешенной пропорциями доступного пространства. Например, если две строки имеют <xref:System.Windows.Controls.RowDefinition.Height%2A> "*", каждая из них имеет высоту, которая является половиной доступного пространства.

    Теперь <xref:System.Windows.Controls.Grid> должен содержать следующий код XAML:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Добавить элементы управления

В этом разделе вы обновите пользовательский интерфейс домашней страницы, чтобы отобразить список людей, в которых вы выбрали одного пользователя для отображения отчета о расходах. Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением. Более подробную информацию см. в разделе [Элементы управления](../controls/index.md).

Чтобы создать этот пользовательский интерфейс, добавьте в *`ExpenseItHome.xaml`* следующие элементы:

- <xref:System.Windows.Controls.ListBox> (для списка пользователей).
- <xref:System.Windows.Controls.Label> (для заголовка списка).
- <xref:System.Windows.Controls.Button> (щелкните, чтобы просмотреть отчет о расходах для пользователя, выбранного в списке).

Каждый элемент управления помещается в строку <xref:System.Windows.Controls.Grid> путем установки присоединенного <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> свойства. Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).

1. В *`ExpenseItHome.xaml`* добавьте в теги <xref:System.Windows.Controls.Grid> следующий код XAML:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > Можно также создать элементы управления, перетащив их из окна **панель элементов** в окно конструктора, а затем задав их свойства в окне **свойства** .

2. Выполните сборку и запуск приложения.

    На следующем рисунке показаны созданные элементы управления.

![Пример снимка экрана ExpenseIt, отображающий список имен](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Добавление изображения и заголовка

В этом разделе вы обновите пользовательский интерфейс домашней страницы, используя изображение и заголовок страницы.

1. В *`ExpenseItHome.xaml`* добавьте еще один столбец в <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> с фиксированной <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселей:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. Добавьте еще одну строку в <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, чтобы всего четыре строки:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. Переместите элементы управления во второй столбец, задав для свойства <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> значение 1 в каждом из трех элементов управления (граница, ListBox и кнопка).

4. Переместите каждый элемент управления по строке, увеличив значение <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> на 1 для каждого из трех элементов управления (границы, ListBox и Button) и для элемента Border.

   Теперь XAML для трех элементов управления выглядит следующим образом:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Задайте для свойства <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> файл изображения *водяного знака. png* , добавив следующий код XAML в любом месте между тегами `<Grid>` и `</Grid>`:

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Перед элементом <xref:System.Windows.Controls.Border> добавьте <xref:System.Windows.Controls.Label> с содержимым "Просмотр отчета о расходах". Эта метка является заголовком страницы.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Выполните сборку и запуск приложения.

На следующем рисунке показаны результаты только что добавленных элементов.

![Образец снимка экрана ExpenseIt, показывающий новый фон и заголовок страницы](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Добавление кода для обработчика событий

1. В *`ExpenseItHome.xaml`* добавьте обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в элемент <xref:System.Windows.Controls.Button>. Дополнительные сведения см. [в разделе инструкции. Создание простого обработчика событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .

3. Добавьте следующий код в класс `ExpenseItHome`, чтобы добавить обработчик событий нажатия кнопки. Обработчик событий открывает страницу **файл ExpenseReportPage** .

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Создание пользовательского интерфейса для файл ExpenseReportPage

*Файл ExpenseReportPage. XAML* отображает отчет о расходах для пользователя, выбранного на странице **`ExpenseItHome`** . В этом разделе вы создадите пользовательский интерфейс для **файл ExpenseReportPage**. Вы также добавите цвета фона и заливки в различные элементы пользовательского интерфейса.

1. Откройте файл *ExpenseReportPage.xaml*.

2. Добавьте следующий код XAML между тегами <xref:System.Windows.Controls.Grid>:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Этот пользовательский интерфейс похож на *`ExpenseItHome.xaml`* , за исключением того, что данные отчета отображаются в <xref:System.Windows.Controls.DataGrid>.

3. Выполните сборку и запуск приложения.

4. Нажмите кнопку **Просмотр** .

    Появится страница отчета по расходам. Также обратите внимание, что кнопка обратной навигации включена.

На следующем рисунке показаны элементы пользовательского интерфейса, добавленные в *файл ExpenseReportPage. XAML*.

![Пример снимка экрана ExpenseIt, показывающий пользовательский интерфейс, созданный для файл ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Элементы управления стиля

Внешний вид различных элементов часто одинаков для всех элементов одного типа в пользовательском интерфейсе. Пользовательский интерфейс использует [стили](../controls/styling-and-templating.md) для того, чтобы внешний вид можно было использовать в нескольких элементах. Многократное использование стилей помогает упростить создание XAML и управление им. В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.

1. Откройте *Application. XAML* или *app. XAML*.

2. Добавьте следующий код XAML между тегами <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Этот код XAML добавляет следующие стили:

    - `headerTextStyle`для форматирования заголовка страницы <xref:System.Windows.Controls.Label>;

    - `labelStyle`для форматирования элементов управления <xref:System.Windows.Controls.Label> ;

    - `columnHeaderStyle`для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>;

    - `listHeaderStyle`для форматирования элементов управления <xref:System.Windows.Controls.Border> заголовков списка;

    - `listHeaderTextStyle`: для форматирования <xref:System.Windows.Controls.Label>заголовка списка.

    - `buttonStyle`: для форматирования <xref:System.Windows.Controls.Button> на `ExpenseItHome.xaml`.

    Обратите внимание, что стили являются ресурсами и дочерними элементами элемента свойства <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>. Здесь стили применяются ко всем элементам в приложении. Пример использования ресурсов в приложении .NET см. в разделе [использование ресурсов приложения](../advanced/how-to-use-application-resources.md).

3. В *`ExpenseItHome.xaml`* замените все между элементами <xref:System.Windows.Controls.Grid> следующим кодом XAML:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются. Например, `headerTextStyle` применяется к <xref:System.Windows.Controls.Label>"Просмотр отчета о расходах".

4. Откройте файл *ExpenseReportPage.xaml*.

5. Замените все элементы <xref:System.Windows.Controls.Grid> элементами следующим кодом XAML:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Этот XAML добавляет стили к элементам <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Border>.

6. Выполните сборку и запуск приложения. Внешний вид окна такой же, как и ранее.

    ![Пример снимка экрана ExpenseIt с тем же видом, что и в последнем разделе.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Закройте приложение, чтобы вернуться в Visual Studio.

## <a name="bind-data-to-a-control"></a>Привязка данных к элементу управления

В этом разделе вы создадите XML-данные, привязанные к различным элементам управления.

1. В *`ExpenseItHome.xaml`* после открытия элемента <xref:System.Windows.Controls.Grid> добавьте следующий код XAML, чтобы создать <xref:System.Windows.Data.XmlDataProvider>, содержащий данные для каждого пользователя:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    Данные создаются в качестве <xref:System.Windows.Controls.Grid> ресурса. Обычно эти данные загружаются в виде файла, но для простоты данные добавляются встроенным образом.

2. В элементе `<Grid.Resources>` добавьте следующий элемент `<xref:System.Windows.DataTemplate>`, который определяет способ отображения данных в <xref:System.Windows.Controls.ListBox>после элемента `<XmlDataProvider>`:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения](../data/data-templating-overview.md)о создании шаблонов данных.

3. Замените существующий <xref:System.Windows.Controls.ListBox> следующим кодом XAML:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Этот XAML привязывает свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox> к источнику данных и применяет шаблон данных в качестве <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.

## <a name="connect-data-to-controls"></a>Подключение данных к элементам управления

Далее предстоит добавить код для получения имени, выбранного на странице **`ExpenseItHome`** , и передать его конструктору **файл ExpenseReportPage**. **Файл ExpenseReportPage** устанавливает в качестве контекста данных переданный элемент, который является элементом управления, определенным в привязке *файл ExpenseReportPage. XAML* к.

1. Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.

2. Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .

4. Измените обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, чтобы вызвать новый конструктор, передающий данные отчета о затратах выбранного человека.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Применение стилей к данным с помощью шаблонов данных

В этом разделе вы обновите пользовательский интерфейс для каждого элемента в списках с привязкой к данным с помощью шаблонов данных.

1. Откройте файл *ExpenseReportPage.xaml*.

2. Привяжите содержимое элементов "Name" и "Department" <xref:System.Windows.Controls.Label> к соответствующему свойству источника данных. Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. После открытия элемента <xref:System.Windows.Controls.Grid> добавьте следующие шаблоны данных, определяющие способ отображения данных отчета о расходах:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Замените элементы <xref:System.Windows.Controls.DataGridTextColumn> <xref:System.Windows.Controls.DataGridTemplateColumn> в элементе <xref:System.Windows.Controls.DataGrid> и примените к ним шаблоны.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Выполните сборку и запуск приложения.

6. Выберите пользователя и нажмите кнопку **Просмотр** .

На следующем рисунке показаны страницы `ExpenseIt`ного приложения с элементами управления, макетом, стилями, привязкой данных и применяемыми шаблонами данных:

![На обеих страницах приложения отображается список имен и отчет о расходах.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> В этом примере демонстрируется конкретная функция WPF, которая не соответствует всем рекомендациям, таким как безопасность, локализация и специальные возможности. Полный охват WPF и рекомендации по разработке приложений .NET см. в следующих разделах:
>
> - [Специальные возможности](../../ui-automation/accessibility-best-practices.md)
> - [Security](../security-wpf.md)
> - [Глобализация и локализация WPF](../advanced/wpf-globalization-and-localization-overview.md)
> - [Производительность WPF](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Следующие шаги

В этом пошаговом руководстве вы узнали о ряде методов создания пользовательского интерфейса с помощью Windows Presentation Foundation (WPF). Теперь у вас должно быть базовое представление о стандартных блоках приложений .NET с привязкой к данным. Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:

- [Архитектура WPF](../advanced/wpf-architecture.md)
- [Обзор XAML (WPF)](../advanced/xaml-overview-wpf.md)
- [Общие сведения о свойствах зависимостей](../advanced/dependency-properties-overview.md)
- [Макет](../advanced/layout.md)

Более подробную информацию о создании приложений см. в следующих разделах:

- [Разработка приложений](../app-development/index.md)
- [Элементы управления](../controls/index.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Графика и мультимедиа](../graphics-multimedia/index.md)
- [Документы в WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>См. также

- [Обзор панелей](../controls/panels-overview.md)
- [Общие сведения о шаблонах данных](../data/data-templating-overview.md)
- [Создание приложения WPF](../app-development/building-a-wpf-application-wpf.md)
- [Стили и шаблоны](../controls/styles-and-templates.md)
