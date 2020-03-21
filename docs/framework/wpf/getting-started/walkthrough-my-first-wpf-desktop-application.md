---
title: Создайте свое первое приложение WPF в Visual Studio 2019 - .NET Framework
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 65b6fe31e86380162e90820c2cf118a9d1b96b4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186586"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Учебник: Создайте свое первое приложение WPF в Visual Studio 2019

В этой статье показано, как разработать настольное приложение Windows Presentation Foundation (WPF), которое включает элементы, общие для большинства приложений WPF: разметка разметки «Расширяемый язык разметки» (XAML), код-за, определения приложений, элементы управления, макет, связывание данных и стили. Для разработки приложения вы будете использовать Visual Studio.

В этом руководстве описано следующее:
> [!div class="checklist"]
>
> - Создайте проект WPF.
> - Используйте XAML для разработки внешнего вида пользовательского интерфейса приложения (UI).
> - Напишите код для построения поведения приложения.
> - Создайте определение приложения для управления приложением.
> - Добавьте элементы управления и создайте макет для составления uI-има приложения.
> - Создавайте стили для последовательного внешнего вида на протяжении всего uI приложения.
> - Привязать uI к данным, как для заполнения uI из данных, так и для синхронизации данных и uI.

К концу учебника вы создали отдельное приложение Windows, которое позволяет пользователям просматривать отчеты о расходах для выбранных людей. Приложение состоит из нескольких страниц WPF, размещенных в окне в стиле браузера.

> [!TIP]
> Образец кода, который используется в этом учебнике, доступен как для Visual Basic, так и для C- в [учебном коде WPF App Sample.](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)
>
> Вы можете переключить кодовый язык кода образца между C и Visual Basic, используя селектор языка поверх этой страницы.

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой для **разработки рабочего стола .NET.**

   Для получения дополнительной информации об установке последней версии Visual Studio, [см.](/visualstudio/install/install-visual-studio)

## <a name="create-the-application-project"></a>Создание проекта приложения

Первым шагом является создание инфраструктуры приложения, которая включает определение приложения, две страницы и изображение.

1. Создайте новый проект приложения WPF в **`ExpenseIt`** Visual Basic или Visual C зпод названием:

   1. Откройте Visual Studio и выберите **Создать новый проект** в меню **Get started.**

      Открывается диалог **«Создание нового проекта».**

   2. В выпадении **языка** выберите либо **C-** или **Visual Basic**.

   3. Выберите шаблон **приложения WPF (.NET Framework),** а затем выберите **следующий**.

      ![Диалоговое окно создания проекта](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      Открывается новый диалог **проекта.**

   4. Введите **`ExpenseIt`** имя проекта, а затем выберите **Создать**.

      ![Настройка нового диалога проекта](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio создает проект и открывает дизайнердля окна приложения по умолчанию под названием **MainWindow.xaml.**

2. Открытое *приложение.xaml* (Visual Basic) или *App.xaml* (C).

    Этот файл XAML определяет приложение WPF и любые ресурсы приложения. Вы также используете этот файл, чтобы указать uI, в данном случае *MainWindow.xaml*, который автоматически показывает, когда приложение начинается.

    Ваш XAML должен выглядеть следующим образом в Visual Basic:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    И, как и следующие в C ':

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Открыть *MainWindow.xaml*.

    Этот файл XAML является основным окном вашего приложения и отображает содержимое, созданное на страницах. Класс <xref:System.Windows.Window> определяет свойства окна, такие как его название, размер или значок, и обрабатывает события, такие как закрытие или сокрытие.

4. Измените <xref:System.Windows.Window> элемент <xref:System.Windows.Navigation.NavigationWindow>на , как показано в следующем XAML:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Это приложение переходит к другому содержимому в зависимости от ввода пользователя. Вот почему главное <xref:System.Windows.Window> должно быть <xref:System.Windows.Navigation.NavigationWindow>изменено на . <xref:System.Windows.Navigation.NavigationWindow>наследует все свойства <xref:System.Windows.Window>. Элемент <xref:System.Windows.Navigation.NavigationWindow> в файле XAML создает <xref:System.Windows.Navigation.NavigationWindow> экземпляр класса. Для получения дополнительной информации смотрите [обзор навигации](../app-development/navigation-overview.md).

5. Удалите <xref:System.Windows.Controls.Grid> элементы <xref:System.Windows.Navigation.NavigationWindow> между тегами.

6. Измените следующие свойства в коде <xref:System.Windows.Navigation.NavigationWindow> XAML для элемента:

    - Установите <xref:System.Windows.Window.Title%2A> свойство`ExpenseIt`на ".

    - Установите <xref:System.Windows.FrameworkElement.Height%2A> свойство до 350 пикселей.

    - Установите <xref:System.Windows.FrameworkElement.Width%2A> свойство до 500 пикселей.

    Ваш XAML должен выглядеть следующим образом для Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    И, как и следующие для C '

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Открыть *MainWindow.xaml.vb* или *MainWindow.xaml.cs*.

    Этот файл представляет собой файл с кодом, содержащий код для обработки событий, заявленных в *MainWindow.xaml.* Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.

8. Если вы используете C-е, `MainWindow` измените <xref:System.Windows.Navigation.NavigationWindow>класс, чтобы извлечь из . (В Visual Basic это происходит автоматически при изменении окна в XAML.) Ваш код C's теперь должен выглядеть следующим образом:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Добавление файлов в приложение

В этом разделе вы добавите в приложение две страницы и изображение.

1. Добавьте новую страницу в *`ExpenseItHome.xaml`* проект и назовите ее:

   1. В **Solution Explorer**, правой кнопкой **`ExpenseIt`** мыши на узло проекта и выбрать **Добавить** > **страницы**.

   1. В диалоге **Добавить новый элемент** уже выбран шаблон **Страницы (WPF).** Введите **`ExpenseItHome`** имя, а затем выберите **Добавить**.

    Эта страница является первой страницей, отображаемыми при запуске приложения. Он покажет список людей, которые можно выбрать из, чтобы показать отчет о расходах для.

1. Открыто *`ExpenseItHome.xaml`*.

1. Установить <xref:System.Windows.Controls.Page.Title%2A> на`ExpenseIt - Home`" "

1. Установите `DesignHeight` до 350 пикселей и `DesignWidth` до 500 пикселей.

    XAML теперь отображается следующим образом для Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    И, как и следующие для C '

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Открыть *MainWindow.xaml*.

1. Добавьте <xref:System.Windows.Navigation.NavigationWindow.Source%2A> свойство <xref:System.Windows.Navigation.NavigationWindow> к элементу`ExpenseItHome.xaml`и установите его на ".

    Это *`ExpenseItHome.xaml`* наборы, чтобы быть первой страницей, открытой при запуске приложения.

    Пример XAML в Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    И в C:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > Вы также можете установить свойство **Source** в **разной** категории окна **Свойства.**
   >
   > ![Источник свойства в окне свойства](./media/properties-source.png)

1. Добавьте в проект еще одну новую страницу WPF и назовите ее *ExpenseReportPage.xaml::*

   1. В **Solution Explorer**, правой кнопкой **`ExpenseIt`** мыши на узло проекта и выбрать **Добавить** > **страницы**.

   1. В диалоге **Добавить новый элемент** выберите шаблон **Страницы (WPF).** Введите имя **ExpenseReportPage,** а затем **выберите Добавить**.

    На этой странице будет отображаться отчет о расходах для выбранного на **`ExpenseItHome`** странице лица.

1. Открыть *ExpenseReportPage.xaml*.

1. Установить <xref:System.Windows.Controls.Page.Title%2A> на`ExpenseIt - View Expense`" "

1. Установите `DesignHeight` до 350 пикселей и `DesignWidth` до 500 пикселей.

    *ExpenseReportPage.xaml* теперь выглядит следующим образом в Visual Basic:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    И, как и следующие в C ':

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Открыть *ExpenseItHome.xaml.vb* и *ExpenseReportPage.xaml.vb*, или *ExpenseItHome.xaml.cs* и *ExpenseReportPage.xaml.cs*.

    При создании нового файла Страницы Visual Studio автоматически создает свой *файл с кодом.* Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.

    Ваш код должен выглядеть **`ExpenseItHome`** следующим образом:

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    И, как следующие для **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Добавьте в проект изображение под названием *watermark.png.* Вы можете создать свое собственное изображение, скопировать файл из кода образца или получить его из репозитория [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub.

    1. Нажмите правой кнопкой мыши на узла проекта и выберите **Добавить** > **существующий элемент,** или нажмите **Shift**+**Alt**+**A.**

    2. В диалоге **Добавить существующий элемент** установите фильтр файла либо для **всех файлов** или **файлов изображений,** просмотрите файл изображения, который вы хотите использовать, а затем выберите **Добавить.**

## <a name="build-and-run-the-application"></a>Создание и запуск приложения

1. Чтобы создать и запустить приложение, нажмите **F5** или выберите **Start Debugging** из меню **Debug.**

    На следующей иллюстрации <xref:System.Windows.Navigation.NavigationWindow> показано приложение с кнопками:

    ![Приложение после создания и запуска его.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Закройте приложение, чтобы вернуться в Visual Studio.

## <a name="create-the-layout"></a>Создание макета

Layout предоставляет упорядоченный способ размещения элементов uI, а также управляет размером и положением этих элементов при повторном размере uI. Обычно макет создается с одним из следующих элементов управления макетом.

- <xref:System.Windows.Controls.Canvas>- Определяет область, в которой вы можете явно позиционировать элементы ребенка, используя координаты, которые относятся к области Canvas.
- <xref:System.Windows.Controls.DockPanel>- Определяет область, где вы можете расположить элементы ребенка либо горизонтально, либо вертикально, по отношению друг к другу.
- <xref:System.Windows.Controls.Grid>- Определяет гибкую область сетки, которая состоит из столбцов и строк.
- <xref:System.Windows.Controls.StackPanel>- Упорядочить элементы ребенка в одну линию, которая может быть ориентирована горизонтально или вертикально.
- <xref:System.Windows.Controls.VirtualizingStackPanel>- Организует и виртуализирует контент на одной линии, которая ориентирована либо горизонтально, либо вертикально.
- <xref:System.Windows.Controls.WrapPanel>- Позиции элементы ребенка в последовательном положении слева направо, нарушая содержимое следующей строки на краю содержащего окна. Последующий заказ происходит последовательно сверху вниз или справа налево, в зависимости от стоимости свойства Ориентации.

Каждый из этих элементов расположения макета поддерживает определенный тип макета для своих элементов ребенка. `ExpenseIt`страницы могут быть изменены, и каждая страница имеет элементы, которые расположены горизонтально и вертикально наряду с другими элементами. В этом примере используется элемент <xref:System.Windows.Controls.Grid> макета для приложения.

> [!TIP]
> Для получения <xref:System.Windows.Controls.Panel> дополнительной информации об элементах [см.](../controls/panels-overview.md) Для получения дополнительной информации [Layout](../advanced/layout.md)о макете см.

В этом разделе создается таблица с одной колонкой с тремя рядами и 10-пиксельной маржой, добавляя определения столбца и строки <xref:System.Windows.Controls.Grid> в *`ExpenseItHome.xaml`*.

1. В *`ExpenseItHome.xaml`*, <xref:System.Windows.FrameworkElement.Margin%2A> установить <xref:System.Windows.Controls.Grid> свойство на элементе "10,0,10,10", что соответствует левой, верхней, правой и нижней поля:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > Вы также можете установить значения **маржи** в окне **свойств** под категорией **Layout:**
   >
   > ![Значения маржи в окне свойств](./media/properties-margin.png)

2. Добавьте следующие XAML между <xref:System.Windows.Controls.Grid> тегами, чтобы создать определения строки и столбца:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Двух <xref:System.Windows.Controls.RowDefinition.Height%2A> строк установлен, что <xref:System.Windows.GridLength.Auto%2A>означает, что ряды размером в зависимости от содержимого строк. По <xref:System.Windows.Controls.RowDefinition.Height%2A> умолчанию размер, <xref:System.Windows.GridUnitType.Star> что означает, что высота строки представляет собой взвешенную долю доступного пространства. Например, если в двух <xref:System.Windows.Controls.RowDefinition.Height%2A> строках есть "к", каждый из них имеет высоту, которая составляет половину имеющегося пространства.

    Теперь <xref:System.Windows.Controls.Grid> ваш должен содержать следующие XAML:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Добавление элементов управления

В этом разделе вы обновите ui-образного веб-страницы, чтобы показать список людей, где вы выбираете одного человека для отображения отчета о расходах. Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением. Для получения дополнительной информации [см.](../controls/index.md)

Чтобы создать этот uI, вы добавите *`ExpenseItHome.xaml`* следующие элементы к:

- A <xref:System.Windows.Controls.ListBox> (для списка людей).
- A <xref:System.Windows.Controls.Label> (для заголовка списка).
- A <xref:System.Windows.Controls.Button> (нажмите кнопку, чтобы просмотреть отчет о расходах для человека, выбранного в списке).

Каждый элемент управления помещается <xref:System.Windows.Controls.Grid> в <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> ряд прилагаемого свойства. Для получения дополнительной информации [Attached Properties Overview](../advanced/attached-properties-overview.md)о прилагаемых свойствах см.

1. В *`ExpenseItHome.xaml`*, добавить следующее XAML где-то между <xref:System.Windows.Controls.Grid> тегами:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > Вы также можете создать элементы управления, перетащив их из окна **Toolbox** в окно проектирования, а затем установив их свойства в окне **Свойств.**

2. Выполните сборку и запустите приложение.

    На следующей иллюстрации показаны созданные вами элементы управления:

![Анализ скриншота ExpenseIt отображает список имен](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Добавление изображения и заголовка

В этом разделе вы обновите uI домашней страницы с изображением и заголовком страницы.

1. В *`ExpenseItHome.xaml`*, добавить <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> еще один <xref:System.Windows.Controls.ColumnDefinition.Width%2A> столбец с фиксированной 230 пикселей:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. Добавьте еще <xref:System.Windows.Controls.Grid.RowDefinitions%2A>один ряд в , в общей сложности четыре строки:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. Переместите элементы управления <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> во второй столбец, установив свойство до 1 в каждом из трех элементов управления (граница, ListBox и кнопка).

4. Переместите каждый элемент управления <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> вниз по ряду, прививего его значение на 1 для каждого из трех элементов управления (граница, ListBox и кнопка) и для элемента границы.

   XAML для трех элементов управления теперь выглядит следующим образом:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Установите <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> свойство к файлу изображения *watermark.png,* добавив следующее XAML где-нибудь между `<Grid>` тегами: `</Grid>`

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Перед <xref:System.Windows.Controls.Border> элементом добавьте <xref:System.Windows.Controls.Label> с содержанием "View Expense Report". Эта метка является названием страницы.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Выполните сборку и запустите приложение.

Следующая иллюстрация показывает результаты того, что вы только что добавили:

![ExpenseIt образец скриншот с указанием нового фона изображения и название страницы](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Добавление кода для обработки событий

1. В *`ExpenseItHome.xaml`* элементе <xref:System.Windows.Controls.Primitives.ButtonBase.Click> добавьте <xref:System.Windows.Controls.Button> обработчик событий. Для получения дополнительной информации [см. Как: Создать простой обработчик событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Открыть *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* или .

3. Добавьте следующий `ExpenseItHome` код в класс, чтобы добавить обработчик события кнопки. Обработчик событий открывает страницу **ExpenseReportPage.**

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Создание uii для ExpenseReportPage

*ExpenseReportPage.xaml* отображает отчет о расходах для человека, **`ExpenseItHome`** выбранного на странице. В этом разделе вы создадите ui ii для **ExpenseReportPage**. Вы также добавите фон и заполните цвета различных элементов uI.

1. Открыть *ExpenseReportPage.xaml*.

2. Добавьте следующие XAML между <xref:System.Windows.Controls.Grid> тегами:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Этот uI похож *`ExpenseItHome.xaml`* на, за исключением отчета <xref:System.Windows.Controls.DataGrid>данные отображаются в .

3. Выполните сборку и запустите приложение.

4. Выберите кнопку **«Вид».**

    Появится страница отчета по расходам. Также обратите внимание, что кнопка обратной навигации включена.

На следующей иллюстрации показаны элементы uI, добавленные в *ExpenseReportPage.xaml.*

![ExpenseIt образец скриншот с указанием uI только что созданный для ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Элементы управления стилем

Появление различных элементов часто одинаково для всех элементов одного типа в uI. UI использует [стили,](../controls/styling-and-templating.md) чтобы сделать выступления многоразовыми для нескольких элементов. Повторное использование стилей помогает упростить создание и управление XAML. В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.

1. Открытое *application.xaml* или *App.xaml*.

2. Добавьте следующие XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> тегами:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Этот код XAML добавляет следующие стили:

    - `headerTextStyle`для форматирования заголовка страницы <xref:System.Windows.Controls.Label>;

    - `labelStyle`для форматирования элементов управления <xref:System.Windows.Controls.Label> ;

    - `columnHeaderStyle`для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>;

    - `listHeaderStyle`для форматирования элементов управления <xref:System.Windows.Controls.Border> заголовков списка;

    - `listHeaderTextStyle`: Для формата <xref:System.Windows.Controls.Label>заголовка списка .

    - `buttonStyle`: Для <xref:System.Windows.Controls.Button> формата на `ExpenseItHome.xaml`.

    Обратите внимание, что стили <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> являются ресурсами и детьми элемента свойства. Здесь стили применяются ко всем элементам в приложении. Например, использование ресурсов в приложении .NET [см.](../advanced/how-to-use-application-resources.md)

3. В *`ExpenseItHome.xaml`*, заменить <xref:System.Windows.Controls.Grid> все между элементами со следующими XAML:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются. Например, `headerTextStyle` применяется к "Отчету <xref:System.Windows.Controls.Label>о расходах просмотра".

4. Открыть *ExpenseReportPage.xaml*.

5. Замените все <xref:System.Windows.Controls.Grid> между элементами следующимXAML:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Это XAML добавляет <xref:System.Windows.Controls.Label> стили к элементам и <xref:System.Windows.Controls.Border> элементам.

6. Выполните сборку и запустите приложение. Внешний вид окна такой же, как и ранее.

    ![ExpenseIt образец скриншот с тем же внешним видом, как и в последнем разделе.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Закройте приложение, чтобы вернуться в Visual Studio.

## <a name="bind-data-to-a-control"></a>Привязка данных к элементу управления

В этом разделе вы создадите данные XML, которые привязаны к различным элементам управления.

1. В *`ExpenseItHome.xaml`*, после <xref:System.Windows.Controls.Grid> открытия элемента, добавить следующий XAML <xref:System.Windows.Data.XmlDataProvider> создать, который содержит данные для каждого человека:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    Данные создаются <xref:System.Windows.Controls.Grid> как ресурс. Обычно эти данные загружаются как файл, но для простоты данные добавляются в строке.

2. В `<Grid.Resources>` элементе добавьте `<xref:System.Windows.DataTemplate>` следующий элемент, определяющий способ <xref:System.Windows.Controls.ListBox>отображения данных в элементе после элемента: `<XmlDataProvider>`

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Для получения дополнительной информации [Data templating overview](../data/data-templating-overview.md)о шаблонах данных см.

3. Замените <xref:System.Windows.Controls.ListBox> существующий на следующий XAML:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Это XAML связывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> источника данных и применяет шаблон <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>данных в качестве .

## <a name="connect-data-to-controls"></a>Подключение данных к элементам управления

Далее вы добавите код для получения выбранного на **`ExpenseItHome`** странице имени и передадут его конструктору **ExpenseReportPage.** **ExpenseReportPage** устанавливает свой контекст данных с пройденный элемент, который является то, что элемент, определенный в *ExpenseReportPage.xaml* связывать.

1. Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.

2. Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Открыть *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* или .

4. Измените <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий, чтобы вызвать новый конструктор, передающий данные отчета о расходах выбранного человека.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Данные о стиле с шаблонами данных

В этом разделе вы будете обновлять ui для каждого элемента в списках, связанных с данными, с помощью шаблонов данных.

1. Открыть *ExpenseReportPage.xaml*.

2. Привязать содержимое элементов "Имя" <xref:System.Windows.Controls.Label> и "Департамент" к соответствующему свойству источника данных. Для получения дополнительной информации [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md)о привязке данных см.

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. После открытия <xref:System.Windows.Controls.Grid> элемента добавьте следующие шаблоны данных, которые определяют, как отображать данные отчета о расходах:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Замените <xref:System.Windows.Controls.DataGridTextColumn> элементы <xref:System.Windows.Controls.DataGridTemplateColumn> <xref:System.Windows.Controls.DataGrid> под элементом и примените к ним шаблоны.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Выполните сборку и запустите приложение.

6. Выберите человека, а затем выберите кнопку **«Вид».**

На следующей иллюстрации `ExpenseIt` показаны обе страницы приложения с элементами управления, макетом, стилями, привязкой данных и прикладными шаблонами данных:

![Обе страницы приложения, показывающие список имен и отчет о расходах.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> Этот пример демонстрирует особенность WPF и не соответствует всем рекомендациям по таким вещам, как безопасность, локализация и доступность. Для всестороннего охвата wPF и передового опыта разработки приложений .NET см.
>
> - [Доступность](../../ui-automation/accessibility-best-practices.md)
> - [Безопасность](../security-wpf.md)
> - [Глобализация и локализация WPF](../advanced/wpf-globalization-and-localization-overview.md)
> - [Производительность WPF](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Дальнейшие действия

В этом пошаге вы узнали ряд методов для создания uI с помощью Windows Презентация фонда (WPF). Теперь вы должны иметь базовое представление о строительных блоках приложения .NET, связанного с данными. Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:

- [Архитектура WPF](../advanced/wpf-architecture.md)
- [Обзор XAML (WPF)](../advanced/xaml-overview-wpf.md)
- [Обзор свойств зависимостей](../advanced/dependency-properties-overview.md)
- [Макет](../advanced/layout.md)

Более подробную информацию о создании приложений см. в следующих разделах:

- [Разработка приложений](../app-development/index.md)
- [Управление](../controls/index.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Графика и мультимедиа](../graphics-multimedia/index.md)
- [Документы в WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>См. также раздел

- [Обзор панелей](../controls/panels-overview.md)
- [Обзор шаблонов данных](../data/data-templating-overview.md)
- [Создание приложения WPF](../app-development/building-a-wpf-application-wpf.md)
- [Стили и шаблоны](../controls/styles-and-templates.md)
