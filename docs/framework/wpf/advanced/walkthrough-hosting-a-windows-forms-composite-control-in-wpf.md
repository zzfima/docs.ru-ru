---
title: "Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF | Microsoft Docs"
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
  - "составные элементы управления, размещение в WPF"
  - "размещение элементов управления Windows Forms в WPF"
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF
Клиент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений.  Однако при создании сложного кода [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] более эффективно использовать по крайней мере часть этого кода повторно в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вместо того, чтобы переписывать его заново.  Наиболее распространенной ситуацией является наличие элементов управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  В некоторых случаях доступ к исходному коду этих элементов управления может даже отсутствовать.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет простую процедуру для размещения таких элементов управления в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Например, можно использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в значительной части программирования при размещении специализированных элементов управления <xref:System.Windows.Forms.DataGridView>.  
  
 В данном пошаговом руководстве создается приложение, в котором содержится составной элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] для поддержки ввода данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Составной элемент управления упакован в библиотеку DLL.  Эта общая процедура может быть расширена для более сложных приложений и элементов управления.  Это пошаговое руководство почти идентично повторяет свойства и функциональные возможности, описанные в разделе [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).  Основным различием является то, что скрипт размещения выполняется в обратном порядке.  
  
 Данное пошаговое руководство разделено на два раздела.  В первом разделе кратко описывается реализация составного элемента управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  Во втором разделе подробно рассматривается размещение составного элемента управления в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], получение событий из элемента управления и доступ к некоторым свойствам элемента управления.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Реализация составного элемента управления Windows Forms.  
  
-   Реализация ведущего приложения WPF.  
  
 Полный пример кода для задач, приведенных в этом руководстве, см. в разделе [Пример размещения составного элемента управления Windows Forms в приложении WPF](http://go.microsoft.com/fwlink/?LinkID=159999).  
  
## Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Реализация составного элемента управления Windows Forms  
 Составной элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)], используемый этом примере, является простой формой ввода данных.  Эта форма принимает имя и адрес пользователя и затем использует пользовательское событие для возвращения сведений узлу.  На следующем рисунке показан отображаемый элемент управления.  
  
 ![Простой элемент управления Windows Forms](../../../../docs/framework/wpf/advanced/media/wfcontrol.png "WFControl")  
Составной элемент управления Windows Forms  
  
### Создание проекта  
 Для запуска проекта выполните следующие действия.  
  
1.  Запустите среду [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] и откройте диалоговое окно **Новый проект**.  
  
2.  В категории Windows выберите шаблон **Библиотека элементов управления Windows Forms**.  
  
3.  Присвойте проекту имя `MyControls`.  
  
4.  В качестве расположения задайте папку верхнего уровня с понятным именем, например `WpfHostingWindowsFormsControl`.  Позже ведущее приложение будет помещено в эту папку.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект.  По умолчанию проект содержит одну страницу с именем `UserControl1`.  
  
6.  В обозревателе решений переименуйте элемент управления `UserControl1` в `MyControl1`.  
  
 Проект должен иметь ссылки на следующие системные библиотеки DLL.  Если любая из этих DLL не включена по умолчанию, добавьте ее в проект.  
  
-   Система  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### Добавление элементов управления в форму  
 Для добавления элементов управления в форму выполните следующие действия:  
  
-   Откройте `MyControl1` в конструкторе.  
  
 Добавьте в форму пять элементов управления <xref:System.Windows.Forms.Label> и соответствующие им элементы управления <xref:System.Windows.Forms.TextBox> с такими же размерами и положением, как на предыдущем рисунке.  В примере элементы управления <xref:System.Windows.Forms.TextBox> называются:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Добавьте два элемента управления <xref:System.Windows.Forms.Button> с заголовками **ОК** и **Отмена**.  В примере кнопки соответственно называются `btnOK` и `btnCancel`.  
  
### Реализация кода поддержки  
 Откройте форму в представлении кода.  Элемент управления возвращает введенные данные на узел путем вызова пользовательского события `OnButtonClick`.  Данные содержатся в объекте аргумента события.  В следующем примере кода показано объявление события и делегата.  
  
 Добавьте в класс `MyControl1` следующий код.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 Класс `MyControlEventArgs` содержит сведения, которые нужно вернуть на узел.  
  
 Добавьте в форму следующий класс.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 Когда пользователь нажимает кнопку **ОК** или **Отмена**, обработчики событий <xref:System.Windows.Forms.Control.Click> создают объект `MyControlEventArgs`, содержащий данные, и вызывает событие `OnButtonClick`.  Единственным отличием между двумя обработчиками является свойство `IsOK` аргумента события.  Это свойство позволяет узлу определить, какая кнопка была нажата.  Оно имеет значение `true` для кнопки **ОК** и `false` для кнопки **Отмена**.  В следующем коде показаны два обработчика кнопок.  
  
 Добавьте в класс `MyControl1` следующий код.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### Задание сборки строгого имени и построение сборки  
 Для того, чтобы данная сборка ссылалась на приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], она должна иметь строгое имя.  Для создания строгого имени создайте файла ключа с помощью Sn.exe и добавьте его в проект.  
  
1.  Откройте командную строку [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  Для этого нажмите кнопку **Пуск** и выберите **Все программы\/Microsoft Visual Studio 2010\/Visual Studio Tools\/Командная строка Visual Studio**.  Будет запущено окно консоли с настраиваемыми переменными среды.  
  
2.  В командной строке перейдите к папке проекта с помощью команды `cd`.  
  
3.  Создайте файл ключа с именем MyControls.snk, выполнив следующую команду.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  Чтобы включить файл ключа в проект, щелкните правой кнопкой мыши имя проекта в обозревателе решений и выберите пункт **Свойства**.  На вкладке **Добавление подписи** конструктора проектов установите флажок **Подписать сборку** и перейдите к файлу ключа.  
  
5.  Выполните построение решения.  Построение создаст DLL с именем MyControls.dll.  
  
## Реализация ведущего приложения WPF  
 Хост\-приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> для размещения `MyControl1`.  Приложение обрабатывает событие `OnButtonClick` для получения данных из элемента управления.  В нем также есть набор переключателей, позволяющих изменить некоторые свойства элемента управления в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Ниже показано завершенное приложение.  
  
 ![Элемент управления, встроенный в страницу WPF](../../../../docs/framework/wpf/advanced/media/avalonhost.png "AvalonHost")  
Завершенное приложение, в котором отображается элемент управления, внедренный в приложение WPF  
  
### Создание проекта  
 Для запуска проекта выполните следующие действия.  
  
1.  Откройте [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] и выберите **Создать проект**.  
  
2.  В категории Windows выберите шаблон **Приложение WPF**.  
  
3.  Присвойте проекту имя `WpfHost`.  
  
4.  В качестве расположение укажите ту же папку верхнего уровня, в которой содержится проект MyControls.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект.  
  
 Также необходимо добавить ссылки на библиотеку DLL, содержащую элемент управления `MyControl1` и другие сборки.  
  
1.  Щелкните правой кнопкой мыши имя проекта в обозревателе решений и выберите команду **Добавить ссылку**.  
  
2.  Перейдите на вкладку **Обзор** и укажите папку, которая содержит файл MyControls.dll.  В данном пошаговом руководстве это папка MyControls\\bin\\Debug.  
  
3.  Выберите файл MyControls.dll и нажмите кнопку **ОК**.  
  
4.  Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration.dll.  
  
### Реализация базовой разметки  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] ведущего приложения реализуется в файле MainWindow.xaml.  Этот файл содержит разметку [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], которая определяет макет и размещает элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  Приложение разделено на три области.  
  
-   Панель **Свойства элемента управления**, которая содержит коллекцию переключателей, которые можно использовать для изменения различных свойств размещаемого элемента управления.  
  
-   Панель **Данные элемента управления**, которая содержит несколько элементов <xref:System.Windows.Controls.TextBlock>, отображающих возвращаемые данные размещенного элемента управления.  
  
-   Сам размещаемый элемент управления.  
  
 В следующем коде XAML показан базовый макет.  Разметка, необходимая для размещения элемента управления `MyControl1`, опущена в этом примере, но будет рассмотрена позднее.  
  
 Замените код XAML в файле MainWindow.xaml следующим кодом.  Если используется язык Visual Basic, измените класс на `x:Class="MainWindow"`.  
  
 [!code-xml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 Первый элемент <xref:System.Windows.Controls.StackPanel> содержит несколько наборов элементов управления <xref:System.Windows.Controls.RadioButton>, позволяющих изменять различные свойства по умолчанию размещаемого элемента управления.  Затем следует элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, который содержит `MyControl1`.  Последний элемент <xref:System.Windows.Controls.StackPanel> содержит несколько элементов <xref:System.Windows.Controls.TextBlock>, отображающих данные, возвращаемые размещаемым элементом управления.  Порядок элементов и параметров атрибутов <xref:System.Windows.Controls.DockPanel.Dock%2A> и <xref:System.Windows.FrameworkElement.Height%2A> внедряет размещаемый элемент управления в окно без пропусков или искажения.  
  
#### Размещение элемента управления  
 В следующей измененной версии предыдущего кода XAML уделяется внимание элементам, необходимым для размещения элемента управления `MyControl1`.  
  
 [!code-xml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 Атрибут сопоставления пространства имен `xmlns` создает ссылку на пространство имен `MyControls`, содержащее размещаемый элемент управления.  Такое сопоставление позволяет представлять `MyControl1` в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] как `<mcl:MyControl1>`.  
  
 Два элемента в коде XAML обрабатывают размещение:  
  
-   `WindowsFormsHost` представляет элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, который позволяет разместить элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   `mcl:MyControl1`, который представляет `MyControl1`, добавляется к дочерней коллекции элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  В результате этот элемент управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] отображается как часть окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и с элементом управления можно взаимодействовать из приложения.  
  
### Реализация файла кода программной части  
 Файл кода программной части MainWindow.xaml.vb или MainWindow.xaml.cs содержит процедурный код, реализующий функциональные возможности [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], рассмотренные в предыдущем разделе.  Основные задачи:  
  
-   Присоединение обработчика событий к событию `MyControl1` `OnButtonClick`.  
  
-   Изменение различных свойств `MyControl1` в зависимости от способа установки коллекции переключателей.  
  
-   Отображение данных, собранных элементом управления.  
  
#### Инициализация приложения  
 Код инициализации содержится в обработчике событий <xref:System.Windows.FrameworkElement.Loaded> окна; он присоединяет обработчик событий к событию `OnButtonClick` элемента управления.  
  
 В файле MainWindow.xaml.vb или MainWindow.xaml.cs добавьте следующий код в класс `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 Поскольку ранее рассмотренный код [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] добавил элемент управления `MyControl1` в коллекцию дочерних элементов элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, можно привести свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, чтобы получить ссылку на элемент управления `MyControl1`.  Затем можно использовать эту ссылку для присоединения обработчика событий к `OnButtonClick`.  
  
 Помимо ссылки на сам элемент управления, <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет ряд свойств элемента управления, которыми можно управлять из приложения.  Код инициализации назначает эти значения закрытых глобальных переменных для последующего использования в приложении.  
  
 Для обеспечения удобного доступа к типам из библиотеки DLL `MyControls`, добавьте следующий оператор `Imports` или `using` в начало файла.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### Обработка события OnButtonClick  
 `MyControl1` вызывает событие `OnButtonClick` при щелчке по любой из кнопок элемента управления.  
  
 Добавьте в класс `MainWindow` следующий код.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 Данные в текстовых полях упаковываются в объект `MyControlEventArgs`.  При нажатии кнопки **ОК** обработчик событий извлекает данные и отображает их на панели ниже `MyControl1`.  
  
#### Изменение свойств элемента управления  
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет некоторые свойства по умолчанию для размещаемого элемента управления.  В результате можно изменить внешний вид элемента управления для более точного соответствия стилю приложения.  Наборы переключателей на левой панели позволяют пользователю изменять некоторые свойства цвета и шрифта.  У каждого набора кнопок есть обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, который отслеживает выбор пользовательских переключателей и изменяет соответствующее свойство элемента управления.  
  
 Добавьте в класс `MainWindow` следующий код.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Постройте и запустите приложение.  Добавьте произвольный текст в составной элемент управления Windows Forms и нажмите кнопку **OK**.  Этот текст появится в подписях.  Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в элементе управления.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)