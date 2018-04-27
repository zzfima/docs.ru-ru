---
title: Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f5a3cef6bc2614691584828ff61e0f8ea40b9f95
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако, если имеются существенные преимущества [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] код, он может быть более эффективным, расширение существующего [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложение с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вместо ее переписывания с нуля. Распространенный сценарий — Если требуется внедрить один или несколько элементов управления, реализованных с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении Windows Forms. Дополнительные сведения о настройке элементов управления WPF см. в разделе [настройки элемента управления](../../../../docs/framework/wpf/controls/control-customization.md).  
  
 Это пошаговое руководство можно с помощью приложения, на котором размещена [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления для поддержки ввода данных в приложении Windows Forms. Составной элемент управления упакован в библиотеку DLL. Эта общая процедура может быть расширена для более сложных приложений и элементов управления. В этом пошаговом руководстве, предназначен для почти идентично внешний вид и функциональные возможности для [Пошаговое руководство: размещение составного элемента управления Windows Forms в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md). Основным отличием является то, что сценарий размещения выполняется в обратном порядке.  
  
 Пошаговое руководство состоит из двух разделов. В первом разделе кратко описывается реализация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления. Во втором разделе подробно рассматриваются способы размещения составного элемента управления в приложении Windows Forms, получать события из элемента управления и доступ к некоторым свойствам элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Реализация составного элемента управления WPF  
  
-   Реализация ведущего приложения Windows Forms  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [размещение составного элемента управления WPF в Windows Forms образец](http://go.microsoft.com/fwlink/?LinkID=159996).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="implementing-the-wpf-composite-control"></a>Реализация составного элемента управления WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Составного элемента управления, используемых в этом примере представляет собой форму простого ввода данных, который принимает имя пользователя и адрес. Когда пользователь нажимает одну из двух кнопок, чтобы указать, что задача завершена, элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение. На приведенном ниже рисунке показан отображаемый элемент управления.  
  
 ![Простой элемент управления WPF](../../../../docs/framework/wpf/advanced/media/avaloncontrol.png "AvalonControl")  
Составной элемент управления WPF  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1.  Запустите [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]и откройте **новый проект** диалоговое окно.  
  
2.  В Visual C# и категории Windows выберите **Библиотека пользовательских элементов управления WPF** шаблона.  
  
3.  Присвойте проекту имя `MyControls`.  
  
4.  Для расположения, укажите удобно папка с именем верхнего уровня, например `WindowsFormsHostingWpfControl`. Позже ведущее приложение будет помещено в эту папку.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект. По умолчанию проект содержит одну страницу с именем `UserControl1`.  
  
6.  В обозревателе решений Переименуйте `UserControl1` для `MyControl1`.  
  
 Проект должен иметь ссылки на перечисленные ниже системные библиотеки DLL. Если какие-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.  
  
-   PresentationCore  
  
-   PresentationFramework  
  
-   Система  
  
-   WindowsBase  
  
### <a name="creating-the-user-interface"></a>Создание пользовательского интерфейса  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Для составного элемента управления реализуется с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Составной элемент управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] состоит из пяти <xref:System.Windows.Controls.TextBox> элементов. Каждый <xref:System.Windows.Controls.TextBox> имеет связанный элемент <xref:System.Windows.Controls.TextBlock> элемент, который служит в качестве метки. Существует два <xref:System.Windows.Controls.Button> элементов внизу, **ОК** и **отменить**. При нажатии любой кнопки элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение.  
  
#### <a name="basic-layout"></a>Базовый макет  
 Различные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы содержатся в <xref:System.Windows.Controls.Grid> элемент. Можно использовать <xref:System.Windows.Controls.Grid> для размещения содержимого составного элемента управления практически таким же, каким образом следует использовать `Table` элемент в формате HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также имеет <xref:System.Windows.Documents.Table> элемент, но <xref:System.Windows.Controls.Grid> является более простым и лучше подходят для задач простую структуру.  
  
 В приведенном ниже коде XAML показан базовый макет. Этот код XAML определяет общую структуру элемента управления, указывая число столбцов и строк в <xref:System.Windows.Controls.Grid> элемент.  
  
 В файле MyControl1.xaml замените имеющийся код XAML приведенным ниже кодом.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Добавление в сетку элементов TextBlock и TextBox  
 Поместить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемента в сетке, задав элемента <xref:System.Windows.Controls.Grid.RowProperty> и <xref:System.Windows.Controls.Grid.ColumnProperty> атрибутов к соответствующему числу строк и столбцов. Следует помнить, что нумерация строк и столбцов ведется от нуля. Имеется элемент охватывает несколько столбцов, установив его <xref:System.Windows.Controls.Grid.ColumnSpanProperty> атрибута. Дополнительные сведения о <xref:System.Windows.Controls.Grid> см [Создание элемента сетки](../../../../docs/framework/wpf/controls/how-to-create-a-grid-element.md).  
  
 Следующий пример XAML составного элемента управления <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.TextBlock> элементы с их <xref:System.Windows.Controls.Grid.RowProperty> и <xref:System.Windows.Controls.Grid.ColumnProperty> атрибутов, которые устанавливаются в правильное расположение элементов в сетке.  
  
 В файле MyControl1.xaml, добавьте следующий код XAML в пределах <xref:System.Windows.Controls.Grid> элемента.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Создание стилей элементов пользовательского интерфейса  
 Многие элементы в форме для ввода данных имеют одинаковый внешний вид. Это означает, что они имеют одинаковые значения нескольких свойств. Вместо того чтобы задавать атрибуты каждого элемента в отдельности предыдущего кода XAML использует <xref:System.Windows.Style> элементов для определения стандартных параметров свойств классов элементов. Такой подход упрощает элемент управления и позволяет изменять внешний вид нескольких элементов посредством одного атрибута стиля.  
  
 <xref:System.Windows.Style> Элементы содержатся в <xref:System.Windows.Controls.Grid> элемента <xref:System.Windows.FrameworkElement.Resources%2A> свойства, поэтому они могут использоваться всеми элементами в элементе управления. Если стиль имеет имя, можно применить его к элементу путем добавления <xref:System.Windows.Style> элементу присвоено имя стиля. Неименованные стили становятся стилями по умолчанию для элемента. Дополнительные сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] стили, в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 В следующем XAML показан <xref:System.Windows.Style> элементы для составного элемента управления. Чтобы увидеть, как стили применяются к элементам, см. предыдущий код XAML. Например, последний <xref:System.Windows.Controls.TextBlock> элемент имеет `inlineText` стиль, а в последнем <xref:System.Windows.Controls.TextBox> элемента используется стиль по умолчанию.  
  
 В файле MyControl1.xaml, добавьте следующий код XAML сразу после <xref:System.Windows.Controls.Grid> начальный элемент.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Добавление кнопок OK и "Отмена"  
 Окончательный элементы составного элемента управления, **ОК** и **отменить** <xref:System.Windows.Controls.Button> элементы, которые занимают первые два столбца последней строки <xref:System.Windows.Controls.Grid>. Эти элементы используют общий обработчик событий `ButtonClicked`и значение по умолчанию <xref:System.Windows.Controls.Button> стиль, определенный в предыдущем коде XAML.  
  
 В файле MyControl1.xaml, добавьте следующий код XAML после последнего <xref:System.Windows.Controls.TextBox> элемента. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Часть составного элемента управления завершена.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Реализация файла кода программной части  
 Файл кода программной части MyControl1.xaml.cs реализует три основные задачи:
  
1.  обрабатывает событие, когда пользователь нажимает одну из кнопок;  
  
2.  Извлекает данные из <xref:System.Windows.Controls.TextBox> элементов и упаковывает его в объект аргумента пользовательского события.  
  
3.  Вызывает пользовательское `OnButtonClick` событие, которое уведомляет узел, что пользователь завершил работу и передает данные на узел.  
  
 Элемент управления также предоставляет ряд свойств цвета и шрифтов, которые позволяют изменять внешний вид. В отличие от <xref:System.Windows.Forms.Integration.WindowsFormsHost> класс, который используется для размещения элемента управления Windows Forms, <xref:System.Windows.Forms.Integration.ElementHost> класс предоставляет элемент управления <xref:System.Windows.Controls.Panel.Background%2A> только свойство. Чтобы обеспечить сходство между этим примером кода и примере, рассмотренном в [Пошаговое руководство: размещение составного элемента управления Windows Forms в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), элемент управления непосредственно предоставляет остальные свойства.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Базовая структура файла кода программной части  
 Файл кода состоит из одного пространства имен, `MyControls`, которая будет содержать два класса `MyControl1` и `MyControlEventArgs`.  
  
```  
namespace MyControls  
{  
  public partial class MyControl1 : Grid  
  {  
    //...  
  }  
  public class MyControlEventArgs : EventArgs  
  {  
    //...  
  }  
}  
```  
  
 Первый класс `MyControl1`, — это разделяемый класс, содержащий код, который реализует функциональность [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] определенных в файле MyControl1.xaml. При анализе файле MyControl1.xaml [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] преобразуется в тот же разделяемый класс, и два разделяемых класса объединяются для формирования скомпилированного элемента управления. По этой причине имя класса в файле кода программной части должно совпадать с именем класса, назначенным в файле MyControl1.xaml, и наследоваться от корневого элемента управления. Второй класс `MyControlEventArgs`, является классом аргументов события, используемый для отправки данных на узел.  
  
 Откройте файл MyControl1.xaml.cs. Измените существующее объявление класса, чтобы он имеет следующее имя и наследует от <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Инициализация элемента управления  
 Приведенный ниже код реализует несколько основных задач:  
  
-   Объявляет частное событие `OnButtonClick`и его связанный делегат `MyControlEventHandler`.  
  
-   создает несколько частных глобальных переменных, хранящих данные пользователя. Эти данные предоставляются через соответствующие свойства;  
  
-   Реализует обработчик `Init`, для элемента управления <xref:System.Windows.FrameworkElement.Loaded> событий. Этот обработчик инициализирует глобальные переменные путем присвоения им значений, определенных в файле MyControl1.xaml. Для этого он использует <xref:System.Windows.FrameworkElement.Name%2A> назначенный типовой <xref:System.Windows.Controls.TextBlock> элемент, `nameLabel`, для доступа к параметрам свойств этого элемента.  
  
 Удалите существующий конструктор и добавьте следующий код, чтобы ваш `MyControl1` класса.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Обработка событий нажатия кнопки  
 Пользователь указывает, что задача ввода данных завершена, либо щелкнув **ОК** кнопку или **отменить** кнопки. Обе кнопки используют тот же <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий `ButtonClicked`. Обе кнопки имеют имя, `btnOK` или `btnCancel`, которое позволяет обработчику определить, какая кнопка была нажата, путем проверки значения `sender` аргумент. Обработчик выполняет следующие действия:  
  
-   Создает `MyControlEventArgs` объект, содержащий данные из <xref:System.Windows.Controls.TextBox> элементов.  
  
-   Если пользователь щелкнет **отменить** кнопку наборы `MyControlEventArgs` объекта `IsOK` свойства `false`.  
  
-   Вызывает `OnButtonClick` событие, указывающее на узел, что пользователь закончил, и передает обратно собранные данные.  
  
 Добавьте следующий код, чтобы ваш `MyControl1` класса после `Init` метод.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Создание свойств  
 Оставшаяся часть класса просто предоставляет свойства, которые соответствуют описанным выше глобальным переменным. При изменении свойства метод доступа set изменяет внешний вид элемента управления путем изменения соответствующих свойств элемента и обновления базовых глобальных переменных.  
  
 Добавьте следующий код, чтобы ваш `MyControl1` класса.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Отправка данных обратно в ведущее приложение  
 Завершающим компонентом в файле является `MyControlEventArgs` класс, который используется для отправки собранных данных обратно на узел.  
  
 Добавьте следующий код, чтобы ваш `MyControls` пространства имен. Реализация является простой и далее не рассматривается.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Постройте решение. В результате сборки будет создана библиотека DLL с именем MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Реализация ведущего приложения Windows Forms  
 Windows Forms разместить приложение использует <xref:System.Windows.Forms.Integration.ElementHost> объект узла [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления. Приложение обрабатывает `OnButtonClick` событий для получения данных из составного элемента управления. Приложение также содержит набор переключателей, которые можно использовать для изменения внешнего вида элемента управления. На рисунке ниже показано приложение.  
  
 ![Размещение элемента управления Avalon, размещаемый Windows Form](../../../../docs/framework/wpf/advanced/media/wfhost.png "WFHost")  
Составной элемент управления WPF в приложении Windows Forms  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1.  Запустите [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]и откройте **новый проект** диалоговое окно.  
  
2.  В Visual C# и категории Windows выберите **приложение Windows Forms** шаблона.  
  
3.  Присвойте проекту имя `WFHost`.  
  
4.  В качестве расположения укажите ту же папку верхнего уровня, в которой содержится проект MyControls.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект.  
  
 Необходимо также добавить ссылки на библиотеку DLL, содержащую `MyControl1` и других сборок.  
  
1.  Щелкните правой кнопкой мыши имя проекта в обозревателе решений и выберите **добавить ссылку**.  
  
2.  Нажмите кнопку **Обзор** вкладку и перейдите к папке, которая содержит файл MyControls.dll. В данном пошаговом руководстве это папка MyControls\bin\Debug.  
  
3.  Выберите файл MyControls.dll и нажмите кнопку **ОК**.  
  
4.  Добавьте ссылки на следующие сборки.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   System.Xaml  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>Реализация пользовательского интерфейса для приложения  
 Пользовательский интерфейс приложения Windows Forms содержит несколько элементов управления для взаимодействия с составным элементом управления WPF.  
  
1.  Откройте приложение Form1 в конструкторе Windows Forms.  
  
2.  Увеличьте форму, чтобы разместить элементы управления.  
  
3.  В правом верхнем углу формы добавьте <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> управления для хранения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления.  
  
4.  Добавьте следующие <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> элементов управления в форму.  
  
    |name|Text|  
    |----------|----------|  
    |groupBox1|Цвет фона|  
    |groupBox2|Цвет переднего плана|  
    |groupBox3|Размер шрифта|  
    |groupBox4|Семейство шрифтов|  
    |groupBox5|Стиль шрифта|  
    |groupBox6|Насыщенность шрифта|  
    |groupBox7|Данные из элемента управления|  
  
5.  Добавьте следующие <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> элементы управления <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> элементов управления.  
  
    |GroupBox|name|Text|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|До преобразования|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|До преобразования|  
    |groupBox2|radioForegroundRed|Красный|  
    |groupBox2|radioForegroundYellow|Желтый|  
    |groupBox3|radioSizeOriginal|До преобразования|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|До преобразования|  
    |groupBox4|radioFamilyTimes|Times New Roman Cyr|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|Норм.|  
    |groupBox5|radioStyleItalic|Italic|  
    |groupBox6|radioWeightOriginal|До преобразования|  
    |groupBox6|radioWeightBold|Полужирный|  
  
6.  Добавьте следующие <xref:System.Windows.Forms.Label?displayProperty=nameWithType> до конца управляет <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>. Эти элементы управления отображают данные, возвращенные [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления.  
  
    |GroupBox|name|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Имя.|  
    |groupBox7|lblAddress|Почтовый адрес:|  
    |groupBox7|lblCity|Город:|  
    |groupBox7|lblState|Состояние:|  
    |groupBox7|lblZip|Почтовый индекс:|  
  
### <a name="initializing-the-form"></a>Инициализация формы  
 Код размещения обычно реализуется в виде <xref:System.Windows.Forms.Form.Load> обработчика событий. В следующем коде показано <xref:System.Windows.Forms.Form.Load> обработчик событий, обработчик [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления <xref:System.Windows.FrameworkElement.Loaded> событий и объявления нескольких глобальных переменных, которые будут использоваться позже.  
  
 В конструкторе Windows Forms дважды щелкните форму, чтобы создать <xref:System.Windows.Forms.Form.Load> обработчика событий. Вверху Form1.cs добавьте следующий `using` инструкции.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Замените содержимое существующего `Form1` класса следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 `Form1_Load` Метод в приведенном выше коде показывает общую процедуру размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления:  
  
1.  Создайте новый <xref:System.Windows.Forms.Integration.ElementHost> объекта.  
  
2.  Задайте в качестве <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>.  
  
3.  Добавить <xref:System.Windows.Forms.Integration.ElementHost> управления <xref:System.Windows.Forms.Panel> элемента управления <xref:System.Windows.Forms.Control.Controls%2A> коллекции.  
  
4.  Создайте экземпляр класса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемента управления.  
  
5.  Размещения составного элемента управления в форме, назначив управления <xref:System.Windows.Forms.Integration.ElementHost> элемента управления <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> свойство.  
  
 Остальные две строки в `Form1_Load` метод присоединяющих обработчики событий двух элементов управления:  
  
-   `OnButtonClick` — пользовательское событие, инициированное составного элемента управления, когда пользователь щелкает **ОК** или **отменить** кнопки. Обработайте событие для получения ответа пользователя и сбора всех введенных им данных.  
  
-   <xref:System.Windows.FrameworkElement.Loaded> — стандартное событие, произошедшее в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления при полной загрузки. Это событие используется здесь потому, что для примера необходима инициализация нескольких глобальных переменных свойствами элемента управления. Во время в формате <xref:System.Windows.Forms.Form.Load> событий, элемент управления не полностью загружен, и по-прежнему установлены эти значения `null`. Необходимо дождаться элемента управления <xref:System.Windows.FrameworkElement.Loaded> событие возникает, чтобы получить доступ к этим свойствам.  
  
 <xref:System.Windows.FrameworkElement.Loaded> В предыдущем примере кода показан обработчик событий. `OnButtonClick` Обработчик рассматривается в следующем разделе.  
  
### <a name="handling-onbuttonclick"></a>Обработка события OnButtonClick  
 `OnButtonClick` Событие происходит, когда пользователь нажимает кнопку **ОК** или **отменить** кнопки.  
  
 Обработчик событий проверяет аргумента события `IsOK` поля, чтобы определить, какая кнопка была нажата. `lbl` *Данные* переменные соответствуют <xref:System.Windows.Forms.Label> элементов управления, которые были описаны выше. При нажатии кнопки **ОК** кнопку данные из элемента управления <xref:System.Windows.Controls.TextBox> элементы управления присваиваются соответствующим <xref:System.Windows.Forms.Label> элемента управления. Если пользователь нажимает кнопку **отменить**, <xref:System.Windows.Forms.Label.Text%2A> значения устанавливаются в строки по умолчанию.  
  
 Добавьте следующую кнопку код обработчика событий для нажатия `Form1` класса.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Выполните сборку и запуск приложения. Добавьте текст в составной элемент управления WPF и нажмите кнопку **ОК**. Текст отображается в метках. На данном этапе код для обработки переключателей еще не добавлен.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Изменение внешнего вида элемента управления  
 <xref:System.Windows.Forms.RadioButton> Элементов управления в форме позволит пользователю изменять [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] переднего плана и фона составного элемента управления цветов, а также ряд свойств шрифта. Цвет фона предоставляется <xref:System.Windows.Forms.Integration.ElementHost> объекта. Остальные свойства предоставляются как настраиваемые свойства элемента управления.  
  
 Дважды щелкните каждый <xref:System.Windows.Forms.RadioButton> управления на форму, чтобы создать <xref:System.Windows.Forms.RadioButton.CheckedChanged> обработчики событий. Замените <xref:System.Windows.Forms.RadioButton.CheckedChanged> обработчики событий следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Выполните сборку и запуск приложения. Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в составном элементе управления WPF.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
