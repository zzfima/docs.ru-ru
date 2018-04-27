---
title: Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF
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
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe706e92223d868476ac438e98b16cf07bb21259
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Тем не менее, если имеются существенные преимущества в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] код, он может быть более эффективным будет повторное использование по крайней мере часть этого кода в ваш [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения вместо ее переписывания с нуля. Наиболее распространенным сценарием является при наличии существующих элементов управления Windows Forms. В некоторых случаях, возможно, у вас даже нет доступа к исходному коду для этих элементов управления. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет простую процедуру для размещения таких элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения. Например, можно использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для большей части программирования при размещении специализированных <xref:System.Windows.Forms.DataGridView> элементов управления.  
  
 Это пошаговое руководство можно с помощью приложения, на котором размещена составного элемента управления Windows Forms для поддержки ввода данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения. Составной элемент управления упакован в библиотеку DLL. Эта общая процедура может быть расширена для более сложных приложений и элементов управления. В этом пошаговом руководстве, предназначен для почти идентично внешний вид и функциональные возможности для [Пошаговое руководство: размещение составного элемента управления WPF в Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). Основным отличием является то, что сценарий размещения выполняется в обратном порядке.  
  
 Пошаговое руководство состоит из двух разделов. В первом разделе кратко описывается реализация составного элемента управления Windows Forms. Во втором разделе подробно рассматривается размещение составного элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения, получать события из элемента управления и доступ к некоторым свойствам элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Реализация составного элемента управления Windows Forms.  
  
-   Реализация ведущего приложения WPF.  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [размещение составного элемента управления Windows Forms в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="implementing-the-windows-forms-composite-control"></a>Реализация составного элемента управления Windows Forms  
 Составной элемент управления Windows Forms используется в данном примере — это форма простого ввода данных. Эта форма принимает имя и адрес пользователя и затем использует пользовательское событие для возвращения сведений в основное приложение. На приведенном ниже рисунке показан отображаемый элемент управления.  
  
 ![Элемент управления Windows Forms, простой](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")  
Составной элемент управления Windows Forms  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1.  Запустите [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]и откройте **новый проект** диалоговое окно.  
  
2.  В категории «окно» выберите **Библиотека элементов управления Windows Forms** шаблона.  
  
3.  Присвойте проекту имя `MyControls`.  
  
4.  Для расположения, укажите удобно папка с именем верхнего уровня, например `WpfHostingWindowsFormsControl`. Позже ведущее приложение будет помещено в эту папку.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект. По умолчанию проект содержит одну страницу с именем `UserControl1`.  
  
6.  В обозревателе решений Переименуйте `UserControl1` для `MyControl1`.  
  
 Проект должен иметь ссылки на перечисленные ниже системные библиотеки DLL. Если какие-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.  
  
-   Система  
  
-   System.Data  
  
-   System.Drawing;  
  
-   System.Windows.Forms.  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Добавление элементов управления на форму  
 Чтобы добавить элементы управления в форму, выполните следующие действия.  
  
-   Откройте `MyControl1` в конструкторе.  
  
 Добавьте пять <xref:System.Windows.Forms.Label> элементы управления и соответствующие им <xref:System.Windows.Forms.TextBox> элементами управления, размером и положением, как в предыдущем примере, в форме. В примере <xref:System.Windows.Forms.TextBox> именуются элементы управления:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Добавление двух <xref:System.Windows.Forms.Button> элементов управления с метками **ОК** и **отменить**. В приведенном примере являются имена кнопок `btnOK` и `btnCancel`соответственно.  
  
### <a name="implementing-the-supporting-code"></a>Реализация соответствующего кода  
 Откройте форму в представлении кода. Элемент управления возвращает собранные данные на узел путем вызова пользовательского `OnButtonClick` событий. Данные содержатся в объекте аргумента события. В следующем коде показано объявление события и делегата.  
  
 Добавьте следующий код в класс `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 `MyControlEventArgs` Класс содержит информацию, возвращаемую к узлу.  
  
 Добавьте в форму следующий класс.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 Когда пользователь щелкает **ОК** или **отменить** кнопки, <xref:System.Windows.Forms.Control.Click> Создание обработчиков событий `MyControlEventArgs` объект, содержащий данные и вызывает `OnButtonClick` событий. Единственное различие между двумя обработчиками является аргумента события `IsOK` свойство. Это свойство позволяет основному приложению определить, какая кнопка была нажата. Ему присваивается `true` для **ОК** кнопки, и `false` для **отменить** кнопки. В следующем примере кода показаны два обработчика кнопок.  
  
 Добавьте следующий код в класс `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Присвоение сборке строгого имени и построение сборки  
 Для этой сборки, на которые ссылается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение, она должна иметь строгое имя. Для создания строгого имени, создайте файл ключа с помощью Sn.exe и добавьте его в проект.  
  
1.  Откройте командную строку [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]. Чтобы сделать это, нажмите кнопку **запустить** меню, а затем выберите **все программы/Microsoft Studio 2010 или Visual Studio Tools/Visual командной строки Visual Studio**. Откроется окно консоли с настраиваемыми переменными среды.  
  
2.  В командной строке используйте `cd` команду, чтобы перейти к папке проекта.  
  
3.  Создайте файл ключа с именем MyControls.snk, выполнив следующую команду.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  Чтобы включить файл ключа в проект, щелкните правой кнопкой мыши имя проекта в обозревателе решений и выберите **свойства**. В конструкторе проектов щелкните **подписывание** выберите **подписать сборку** флажок, а затем перейдите к файлу ключа.  
  
5.  Постройте решение. Сборка создаст библиотеку DLL с именем MyControls.dll.  
  
## <a name="implementing-the-wpf-host-application"></a>Реализация ведущего приложения WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Разместить приложение использует <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления для размещения `MyControl1`. Приложение обрабатывает `OnButtonClick` событий для получения данных из элемента управления. Он также имеет коллекцию переключателей, можно изменять некоторые свойства элемента управления из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения. Ниже показано готовое приложение.  
  
 ![Элемент управления, встроенный в страницу WPF](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")  
Готовое приложение с встроенным в приложение WPF элементом управления  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1.  Откройте [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]и выберите **новый проект**.  
  
2.  В категории «окно» выберите **приложение WPF** шаблона.
  
3.  Присвойте проекту имя `WpfHost`.  
  
4.  В качестве расположения укажите ту же папку верхнего уровня, в которой содержится проект MyControls.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект.  
  
 Необходимо также добавить ссылки на библиотеку DLL, содержащую `MyControl1` и других сборок.  
  
1.  Щелкните правой кнопкой мыши имя проекта в обозревателе решений и выберите **добавить ссылку**.  
  
2.  Нажмите кнопку **Обзор** вкладку и перейдите к папке, которая содержит файл MyControls.dll. В данном пошаговом руководстве это папка MyControls\bin\Debug.  
  
3.  Выберите файл MyControls.dll и нажмите кнопку **ОК**.  
  
4.  Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration.dll.  
  
### <a name="implementing-the-basic-layout"></a>Реализация базового макета  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Узла реализации приложения в файле MainWindow.xaml. Этот файл содержит [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметку, которая определяет макет и размещает элемент управления Windows Forms. Приложение состоит из трех областей:  
  
-   **Свойства элемента управления** панель, которая содержит коллекцию переключателей, можно использовать для изменения различных свойств размещенного элемента управления.  
  
-   **Данные из элемента управления** панель, которая содержит несколько <xref:System.Windows.Controls.TextBlock> элементы, которые отображают данные, возвращенные размещенного элемента управления.  
  
-   Размещенный элемент.  
  
 Базовый макет показан в следующем XAML-коде. Разметка, которая необходима для размещения `MyControl1` опущен в этом примере, но будет рассмотрен позднее.  
  
 Замените XAML-код в файле MainWindow.xaml следующим. Если вы используете Visual Basic, измените класс, чтобы `x:Class="MainWindow"`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 Первый <xref:System.Windows.Controls.StackPanel> элемент содержит несколько наборов <xref:System.Windows.Controls.RadioButton> элементов управления, которые позволяют изменять различные свойства по умолчанию размещенного элемента управления. За которым следует <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент, какие узлы `MyControl1`. Конечное <xref:System.Windows.Controls.StackPanel> элемент содержит несколько <xref:System.Windows.Controls.TextBlock> элементов, отображающих данные, возвращаемые размещенного элемента управления. Упорядочение элементов и <xref:System.Windows.Controls.DockPanel.Dock%2A> и <xref:System.Windows.FrameworkElement.Height%2A> параметров атрибутов внедрить размещенного элемента управления в окно без пропусков или искажения.  
  
#### <a name="hosting-the-control"></a>Размещение элемента управления  
 В следующей измененной версии предыдущего кода XAML уделяется элементов, которые требуется узел `MyControl1`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 `xmlns` Атрибут сопоставления пространства имен создает ссылку на `MyControls` пространство имен, содержащее размещенного элемента управления. Это сопоставление позволяет представлять `MyControl1` в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] как `<mcl:MyControl1>`.  
  
 Два элемента в коде XAML обрабатывают размещение:  
  
-   `WindowsFormsHost` Представляет <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент, который позволяет размещать элемент управления Windows Forms в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.  
  
-   `mcl:MyControl1`, который представляет `MyControl1`, добавляется <xref:System.Windows.Forms.Integration.WindowsFormsHost> дочерней коллекции элемента. В результате этого элемента управления Windows Forms подготавливается к просмотру как часть [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , после чего можно взаимодействовать с элементом управления из приложения.  
  
### <a name="implementing-the-code-behind-file"></a>Реализация файла кода программной части  
 Файл кода, MainWindow.xaml.vb или MainWindow.xaml.cs содержит процедурный код, который реализует функциональность [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] описано в предыдущем разделе. Основные задачи  
  
-   Присоединение обработчика событий для `MyControl1` `OnButtonClick` событие.  
  
-   Изменение различных свойств `MyControl1`в зависимости от того, каким образом заданы коллекцию переключателей.  
  
-   Отображение данных, собранных с помощью элемента управления.  
  
#### <a name="initializing-the-application"></a>Инициализация приложения  
 Код инициализации содержится в обработчике событий для окна <xref:System.Windows.FrameworkElement.Loaded> событий и присоединяет обработчик событий к элементу управления `OnButtonClick` событий.  
  
 В файле MainWindow.xaml.cs или MainWindow.XAML.vb добавьте следующий код в `MainWindow` класса.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 Поскольку [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] описанные ранее добавленный `MyControl1` для <xref:System.Windows.Forms.Integration.WindowsFormsHost> коллекции дочерних элементов элемента, можно привести <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> для получения ссылки на `MyControl1`. Затем можно использовать эту ссылку для присоединения обработчика событий для `OnButtonClick`.  
  
 Помимо предоставления ссылки на элемент управления, <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет ряд свойств элемента управления, которыми можно управлять из приложения. Код инициализации назначает эти значения закрытым глобальным переменным для последующего использования в приложении.  
  
 Чтобы легко получить доступ к типам в `MyControls` DLL, добавьте следующий `Imports` или `using` инструкции в начало файла.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a>Обработка события OnButtonClick  
 `MyControl1` вызывает `OnButtonClick` событие при щелчке по любой из кнопок элемента управления.  
  
 Добавьте следующий код в класс `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 Данные в текстовых полях, упакована в `MyControlEventArgs` объекта. Если пользователь нажимает кнопку **ОК** кнопку обработчик событий извлекает данные и отображает его в нижней панели `MyControl1`.  
  
#### <a name="modifying-the-controls-properties"></a>Изменение свойств элемента управления  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент предоставляет несколько стандартных свойств размещенного элемента управления. В результате можно изменить внешний вид элемента управления, чтобы он более полно соответствовал стилю приложения. Наборы переключателей на левой панели позволяют пользователю изменять некоторые свойства цвета и шрифта. Каждый набор кнопок имеет обработчик <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие, которое определяет пользователя переключателей и изменяет соответствующее свойство элемента управления.  
  
 Добавьте следующий код в класс `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Выполните сборку и запуск приложения. Добавьте текст в составной элемент управления Windows Forms и нажмите кнопку **ОК**. Текст отображается в метках. Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в элементе управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
