---
title: Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: e30b1bb45cc2dae2783cddf54dda400b742cdf73
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920326"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако при наличии значительных инвестиций в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] код может оказаться более эффективным, чтобы повторно использовать по крайней мере часть этого кода в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а не переписывать его с нуля. Наиболее распространенный сценарий заключается в наличии существующих элементов управления Windows Forms. В некоторых случаях, возможно, у вас даже нет доступа к исходному коду для этих элементов управления. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет простую процедуру размещения таких элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении. Например, можно использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для большей части программирования при размещении специализированных элементов управления <xref:System.Windows.Forms.DataGridView>.  
  
 В этом пошаговом руководстве описано приложение, в котором размещен Windows Forms составной элемент управления для выполнения ввода данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении. Составной элемент управления упакован в библиотеку DLL. Эта общая процедура может быть расширена для более сложных приложений и элементов управления. Это пошаговое руководство призвано стать практически идентичным по внешнему виду и функциональности для [пошагового руководства: размещение составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). Основным отличием является то, что сценарий размещения выполняется в обратном порядке.  
  
 Пошаговое руководство состоит из двух разделов. В первом разделе кратко описывается реализация составного элемента управления Windows Forms. Во втором разделе подробно рассматривается размещение составного элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении, получение событий из элемента управления и доступ к некоторым свойствам элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
- Реализация составного элемента управления Windows Forms.  
  
- Реализация ведущего приложения WPF.  
  
 Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Пример размещения Windows Forms составного элемента управления в WPF](https://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Необходимые компоненты  

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.
  
## <a name="implementing-the-windows-forms-composite-control"></a>Реализация составного элемента управления Windows Forms  
 Windows Forms составной элемент управления, используемый в этом примере, представляет собой простую форму ввода данных. Эта форма принимает имя и адрес пользователя и затем использует пользовательское событие для возвращения сведений в основное приложение. На приведенном ниже рисунке показан отображаемый элемент управления.  

 На следующем рисунке показан Windows Forms составной элемент управления:  

 ![Снимок экрана, на котором показан простой элемент управления Windows Forms.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1. Запустите Visual Studio и откройте диалоговое окно **Создание проекта** .  
  
2. В категории окно выберите шаблон **Библиотека элементов управления Windows Forms** .  
  
3. Присвойте проекту имя `MyControls`.  
  
4. В качестве расположения укажите папку верхнего уровня с удобным именем, например `WpfHostingWindowsFormsControl`. Позже ведущее приложение будет помещено в эту папку.  
  
5. Нажмите кнопку **ОК**, чтобы создать проект. Проект по умолчанию содержит один элемент управления с именем `UserControl1`.  
  
6. В обозреватель решений переименуйте `UserControl1` в `MyControl1`.  
  
 Проект должен иметь ссылки на перечисленные ниже системные библиотеки DLL. Если какие-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.  
  
- Система  
  
- System.Data  
  
- System.Drawing;  
  
- System.Windows.Forms.  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Добавление элементов управления на форму  
 Чтобы добавить элементы управления в форму, выполните следующие действия.  
  
- Откройте `MyControl1` в конструкторе.  
  
 Добавьте пять элементов управления <xref:System.Windows.Forms.Label> и их соответствующие элементы управления <xref:System.Windows.Forms.TextBox>, а также их размер и расположение, как показано на предыдущем рисунке в форме. В этом примере элементы управления <xref:System.Windows.Forms.TextBox> называются:  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 Добавьте два элемента управления <xref:System.Windows.Forms.Button> с меткой **ОК** и **Отмена**. В этом примере имена кнопок `btnOK` и `btnCancel`соответственно.  
  
### <a name="implementing-the-supporting-code"></a>Реализация соответствующего кода  
 Откройте форму в представлении кода. Элемент управления возвращает собранные данные на узел путем вызова пользовательского события `OnButtonClick`. Данные содержатся в объекте аргумента события. В следующем коде показано объявление события и делегата.  
  
 Добавьте следующий код в класс `MyControl1` .  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 Класс `MyControlEventArgs` содержит сведения, которые будут возвращены узлу.

 Добавьте в форму следующий класс.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Когда пользователь нажимает кнопку **ОК** или **Отмена** , обработчики <xref:System.Windows.Forms.Control.Click> событий создают объект `MyControlEventArgs`, содержащий данные, и вызывает событие `OnButtonClick`. Единственное различие между двумя обработчиками — это свойство `IsOK` аргумента события. Это свойство позволяет основному приложению определить, какая кнопка была нажата. Он имеет значение `true` для кнопки **ОК** и `false` для кнопки **Отмена** . В следующем примере кода показаны два обработчика кнопок.

 Добавьте следующий код в класс `MyControl1` .

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Присвоение сборке строгого имени и построение сборки
 Чтобы на эту сборку ссылалось приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], оно должно иметь строгое имя. Чтобы создать строгое имя, создайте файл ключа с помощью программы Sn. exe и добавьте его в проект.

1. Откройте командную строку Visual Studio. Для этого в меню " **Пуск** " выберите **все программы/Microsoft Visual Studio 2010/инструменты Visual Studio/Командная строка Visual Studio**. Откроется окно консоли с настраиваемыми переменными среды.

2. В командной строке выполните команду `cd`, чтобы открыть папку проекта.

3. Создайте файл ключа с именем MyControls.snk, выполнив следующую команду.

    ```console
    Sn.exe -k MyControls.snk
    ```

4. Чтобы включить файл ключа в проект, щелкните правой кнопкой мыши имя проекта в обозреватель решений а затем выберите пункт **Свойства**. В конструкторе проектов перейдите на вкладку **Подписывание** , установите флажок **подписать сборку** и перейдите к файлу ключа.

5. Постройте решение. В результате сборки будет создана библиотека DLL с именем MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Реализация ведущего приложения WPF
 Ведущее приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> для размещения `MyControl1`. Приложение обрабатывает событие `OnButtonClick` для получения данных из элемента управления. Он также содержит коллекцию переключателей, которые позволяют изменять некоторые свойства элемента управления из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения. Ниже показано готовое приложение.

На следующем рисунке показано полное приложение, включая элемент управления, внедренный в приложение WPF:

 ![Снимок экрана, на котором показан элемент управления, внедренный в страницу WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>Создание проекта
 Для запуска проекта выполните указанные ниже действия.

1. Откройте Visual Studio и выберите **создать проект**.

2. В категории окно выберите шаблон **приложение WPF** .

3. Присвойте проекту имя `WpfHost`.

4. В качестве расположения укажите ту же папку верхнего уровня, в которой содержится проект MyControls.

5. Нажмите кнопку **ОК**, чтобы создать проект.

 Также необходимо добавить ссылки на библиотеку DLL, содержащую `MyControl1` и другие сборки.

1. Щелкните правой кнопкой мыши имя проекта в обозреватель решений и выберите команду **Добавить ссылку**.

2. Перейдите на вкладку **Обзор** и перейдите в папку, содержащую файл MyControls. dll. В данном пошаговом руководстве это папка MyControls\bin\Debug.

3. Выберите файл MyControls. dll и нажмите кнопку **ОК**.

4. Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.

### <a name="implementing-the-basic-layout"></a>Реализация базового макета
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] ведущего приложения реализуется в файле MainWindow. XAML. Этот файл содержит [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметку, определяющую макет, и размещает элемент управления Windows Forms. Приложение состоит из трех областей:

- Панель **свойства элемента управления** , которая содержит коллекцию переключателей, которые можно использовать для изменения различных свойств размещенного элемента управления.

- **Данные из панели управления** , которая содержит несколько <xref:System.Windows.Controls.TextBlock> элементов, отображающих данные, возвращаемые размещенным элементом управления.

- Размещенный элемент.

 Базовый макет показан в следующем XAML-коде. Разметка, необходимая для размещения `MyControl1`, пропущена в этом примере, но будет обсуждаться далее.

 Замените XAML-код в файле MainWindow.xaml следующим. Если вы используете Visual Basic, измените класс на `x:Class="MainWindow"`.

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 Первый элемент <xref:System.Windows.Controls.StackPanel> содержит несколько наборов элементов управления <xref:System.Windows.Controls.RadioButton>, которые позволяют изменять различные свойства по умолчанию размещенного элемента управления. За ним следует элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, в котором размещается `MyControl1`. Последний элемент <xref:System.Windows.Controls.StackPanel> содержит несколько элементов <xref:System.Windows.Controls.TextBlock>, которые отображают данные, возвращаемые размещаемым элементом управления. Упорядочивание элементов и параметров атрибутов <xref:System.Windows.Controls.DockPanel.Dock%2A> и <xref:System.Windows.FrameworkElement.Height%2A> внедряет размещаемый элемент управления в окно без пропусков или искажений.

#### <a name="hosting-the-control"></a>Размещение элемента управления
 В следующей измененной версии предыдущего кода XAML основное внимание уделяется элементам, необходимым для размещения `MyControl1`.

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 Атрибут сопоставления пространства имен `xmlns` создает ссылку на `MyControls` пространство имен, содержащее размещенный элемент управления. Это сопоставление позволяет представлять `MyControl1` в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] как `<mcl:MyControl1>`.

 Два элемента в коде XAML обрабатывают размещение:

- `WindowsFormsHost` представляет элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, позволяющий размещать элемент управления Windows Forms в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- `mcl:MyControl1`, представляющий `MyControl1`, добавляется в дочернюю коллекцию элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>. В результате этот Windows Forms элемент управления отображается как часть окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и вы можете взаимодействовать с элементом управления из приложения.

### <a name="implementing-the-code-behind-file"></a>Реализация файла кода программной части
 Файл кода программной части MainWindow. XAML. vb или MainWindow.xaml.cs содержит процедурный код, реализующий функциональные возможности [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], обсуждаемого в предыдущем разделе. Основные задачи

- Присоединение обработчика событий к `OnButtonClick`ному событию `MyControl1`.

- Изменение различных свойств `MyControl1`в зависимости от того, как задается коллекция переключателей.

- Отображение данных, собранных с помощью элемента управления.

#### <a name="initializing-the-application"></a>Инициализация приложения
 Код инициализации содержится в обработчике событий для события <xref:System.Windows.FrameworkElement.Loaded> окна и прикрепляет обработчик событий к событию `OnButtonClick` элемента управления.

 В файле MainWindow. XAML. vb или MainWindow.xaml.cs добавьте следующий код в класс `MainWindow`.

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 Поскольку [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], описанный ранее, добавил `MyControl1` в коллекцию дочерних элементов <xref:System.Windows.Forms.Integration.WindowsFormsHost>, можно привести <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, чтобы получить ссылку на `MyControl1`. Затем эту ссылку можно использовать для присоединения обработчика событий к `OnButtonClick`.

 Помимо предоставления ссылки на сам элемент управления, <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет ряд свойств элемента управления, которыми можно управлять из приложения. Код инициализации назначает эти значения закрытым глобальным переменным для последующего использования в приложении.

 Чтобы можно было легко получить доступ к типам в `MyControls` библиотеке DLL, добавьте в начало файла следующую инструкцию `Imports` или `using`.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Обработка события OnButtonClick
 `MyControl1` вызывает событие `OnButtonClick`, когда пользователь нажимает одну из кнопок элемента управления.

 Добавьте следующий код в класс `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 Данные в текстовых полях упаковываются в объект `MyControlEventArgs`. Если пользователь нажмет кнопку **ОК** , обработчик событий извлекает данные и отображает их на панели ниже `MyControl1`.

#### <a name="modifying-the-controls-properties"></a>Изменение свойств элемента управления
 Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет несколько свойств размещенного элемента управления по умолчанию. В результате можно изменить внешний вид элемента управления, чтобы он более полно соответствовал стилю приложения. Наборы переключателей на левой панели позволяют пользователю изменять некоторые свойства цвета и шрифта. Каждый набор кнопок имеет обработчик события <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, который обнаруживает выбор переключателя пользователем и изменяет соответствующее свойство элемента управления.

 Добавьте следующий код в класс `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Выполните сборку и запуск приложения. Добавьте текст в составной элемент управления Windows Forms и нажмите кнопку **ОК**. Этот текст появится в метках. Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в элементе управления.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
