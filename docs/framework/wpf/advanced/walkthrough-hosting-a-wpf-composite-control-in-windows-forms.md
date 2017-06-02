---
title: "Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms | Microsoft Docs"
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
  - "размещение содержимого WPF в Windows Forms"
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
Клиент [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений.  Однако если имеющийся код [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] содержит важные элементы, более эффективным может быть расширение существующего приложения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с помощью клиента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а не переписывание кода "с нуля".  Один из распространенных сценариев состоит в необходимости внедрения одного или нескольких элементов управления, реализованных с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в приложение [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  Дополнительные сведения о настройке элементов управления WPF см. в разделе [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md).  
  
 В данном пошаговом руководстве создается приложение, в котором содержится составной элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для поддержки ввода данных в [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  Составной элемент управления упакован в библиотеку DLL.  Эта общая процедура может быть расширена для более сложных приложений и элементов управления.  Это пошаговое руководство почти идентично повторяет свойства и функциональные возможности, описанные в разделе [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md).  Основным различием является то, что скрипт размещения выполняется в обратном порядке.  
  
 Данное пошаговое руководство разделено на два раздела.  В первом разделе кратко описывается реализация составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Во втором разделе подробно рассматривается размещение составного элемента управления в приложении [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)], получение событий из элемента управления и доступ к некоторым свойствам элемента управления.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Реализация составного элемента управления WPF  
  
-   Реализация ведущего приложения Windows Forms.  
  
 Полный пример кода для задач, приведенных в этом руководстве, см. в разделе [Пример размещения составного элемента управления Windows Forms в приложении WPF](http://go.microsoft.com/fwlink/?LinkID=159996).  
  
## Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Реализация составного элемента управления WPF  
 Составной элемент управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], используемый в этом примере, представляет собой простую форму ввода данных, содержащую поля для имени пользователя и его адреса.  Когда пользователь нажимает одну из двух кнопок, чтобы указать, что задача завершена, элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение.  На следующем рисунке показан отображаемый элемент управления.  
  
 ![Простой элемент управления WPF](../../../../docs/framework/wpf/advanced/media/avaloncontrol.png "AvalonControl")  
Составной элемент управления WPF  
  
### Создание проекта  
 Для запуска проекта выполните следующие действия.  
  
1.  Запустите среду [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] и откройте диалоговое окно **Новый проект**.  
  
2.  В Visual C\# и категории Windows выберите шаблон **Библиотека пользовательских элементов управления WPF**.  
  
3.  Присвойте проекту имя `MyControls`.  
  
4.  В качестве расположения задайте папку верхнего уровня с понятным именем, например `WindowsFormsHostingWpfControl`.  Позже ведущее приложение будет помещено в эту папку.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект.  По умолчанию проект содержит одну страницу с именем `UserControl1`.  
  
6.  В обозревателе решений переименуйте элемент управления `UserControl1` в `MyControl1`.  
  
 Проект должен иметь ссылки на следующие системные библиотеки DLL.  Если какие\-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.  
  
-   PresentationCore  
  
-   PresentationFramework  
  
-   Система  
  
-   WindowsBase  
  
### Создание пользовательского интерфейса  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для составного элемента управления реализуется с помощью языка [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] составного элемента управления состоит из пяти элементов <xref:System.Windows.Controls.TextBox>.  Каждый элемент <xref:System.Windows.Controls.TextBox> имеет связанный элемент <xref:System.Windows.Controls.TextBlock>, служащий в качестве метки.  В нижней части элемента управления имеются два элемента <xref:System.Windows.Controls.Button> — **OK** и **Cancel**.  При нажатии любой кнопки элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение.  
  
#### Базовый макет  
 В элементе <xref:System.Windows.Controls.Grid> содержатся различные элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Объект <xref:System.Windows.Controls.Grid> используется для размещения содержимого составного элемента управления практически так же, как элемент `Table` в HTML.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также имеется элемент <xref:System.Windows.Documents.Table>, но объект <xref:System.Windows.Controls.Grid> проще использовать; кроме того, с его помощью лучше выполняются простые задачи компоновки.  
  
 В следующем коде XAML показан базовый макет.  Этот код XAML определяет общую структуру элемента управления, указывая число столбцов и строк в элементе <xref:System.Windows.Controls.Grid>.  
  
 В файле MyControl1.xaml замените имеющийся код XAML следующим кодом.  
  
 [!code-xml[WindowsFormsHostingWpfControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xml[WindowsFormsHostingWpfControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### Добавление в сетку элементов TextBlock и TextBox  
 Элемент [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] помещается в сетке посредством задания атрибутам <xref:System.Windows.Controls.Grid.RowProperty> и <xref:System.Windows.Controls.Grid.ColumnProperty> элемента соответствующего номера строки и столбца.  Следует помнить, что нумерация строк и столбцов ведется от нуля.  Можно создать общий элемент для нескольких столбцов, задав атрибут <xref:System.Windows.Controls.Grid.ColumnSpanProperty>.  Дополнительные сведения об элементах <xref:System.Windows.Controls.Grid> см. в разделе [Создание элемента сетки](../../../../docs/framework/wpf/controls/how-to-create-a-grid-element.md).  
  
 В следующем коде XAML показаны элементы <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.TextBlock> составного элемента управления и их атрибуты <xref:System.Windows.Controls.Grid.RowProperty> и <xref:System.Windows.Controls.Grid.ColumnProperty>, с помощью которых задается правильное расположение элементов в сетке.  
  
 В файле MyControl1.xaml добавьте следующий код XAML в элементе <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[WindowsFormsHostingWpfControl#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### Создание стилей элементов пользовательского интерфейса  
 Многие элементы в форме для ввода данных имеют одинаковый внешний вид; это означает, что они имеют одинаковые параметры нескольких свойств.  Вместо того чтобы устанавливать атрибуты отдельно для каждого элемента, в предыдущем коде XAML используются элементы <xref:System.Windows.Style> для определения стандартных параметров свойств классов элементов.  Такой подход упрощает элемент управления и позволяет изменять внешний вид нескольких элементов посредством одного атрибута стиля.  
  
 Элементы <xref:System.Windows.Style> содержатся в свойстве <xref:System.Windows.FrameworkElement.Resources%2A> элемента <xref:System.Windows.Controls.Grid>, поэтому они могут использоваться всеми элементами в элементе управления.  Если стиль поименован, он применяется к элементу посредством добавления набора элементов <xref:System.Windows.Style> к стилю с заданным именем.  Непоименованные стили становятся стилями по умолчанию для элемента.  Дополнительные сведения о стилях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 В следующем коде XAML показаны элементы <xref:System.Windows.Style> для составного элемента управления.  Чтобы увидеть, как стили применяются к элементам, см. предыдущий код XAML.  Например, последний элемент <xref:System.Windows.Controls.TextBlock> имеет стиль `inlineText`, а в последнем элементе <xref:System.Windows.Controls.TextBox> используется стиль по умолчанию.  
  
 В файле MyControl1.xaml добавьте следующий код XAML сразу после начального элемента <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[WindowsFormsHostingWpfControl#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### Добавление кнопок "ОК" и "Отмена"  
 Завершающими элементами составного элемента управления являются элементы <xref:System.Windows.Controls.Button> **OK** и **Cancel**, которые занимают первые два столбца последней строки элемента <xref:System.Windows.Controls.Grid>.  Эти элементы используют общий обработчик событий `ButtonClicked` и стиль по умолчанию <xref:System.Windows.Controls.Button>, определенный в предыдущем коде XAML.  
  
 В файле MyControl1.xaml добавьте следующий код XAML после последнего элемента <xref:System.Windows.Controls.TextBox>.  Часть [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] составного элемента управления завершена.  
  
 [!code-xml[WindowsFormsHostingWpfControl#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### Реализация файла кода программной части  
 Файл кода программной части MyControl1.xaml.cs реализует три важные задачи.  
  
1.  Обрабатывает событие, когда пользователь нажимает одну из кнопок.  
  
2.  Извлекает данные из элементов <xref:System.Windows.Controls.TextBox> и пакует их в объект аргумента пользовательского события.  
  
3.  Вызывает пользовательское событие `OnButtonClick`, которое уведомляет узел, что пользователь завершил работу, и возвращает данные на узел.  
  
 Элемент управления также предоставляет ряд свойств цвета и шрифтов, которые позволяют изменять внешний вид.  В отличие от класса<xref:System.Windows.Forms.Integration.WindowsFormsHost>, который используется для размещения элемента управления [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)], класс <xref:System.Windows.Forms.Integration.ElementHost> предоставляет только свойство <xref:System.Windows.Controls.Panel.Background%2A> элемента управления.  Чтобы обеспечить сходство между этим примером кода и примером, который обсуждается в разделе [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), элемент управления непосредственно предоставляет остальные свойства.  
  
#### Базовая структура файла кода программной части  
 Файл кода программной части содержит одно пространство имен `MyControls`, которое состоит из двух классов — `MyControl1` и `MyControlEventArgs`.  
  
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
  
 Первый класс, `MyControl1`, — это разделяемый класс, содержащий код, который реализует функциональные возможности [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], определенного в файле MyControl1.xaml.  При синтаксическом анализе файла MyControl1.xaml код [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] преобразуется в тот же разделяемый класс, и два разделяемых класса объединяются для формирования скомпилированного элемента управления.  По этой причине имя класса в файле кода программной части должно совпадать с именем класса, назначенным в файле MyControl1.xaml, и оно должно наследоваться от корневого элемента элемента управления.  Второй класс `MyControlEventArgs` является классом аргументов события, который используется для возвращения данных на узел.  
  
 Откройте файл MyControl1.xaml.cs.  Измените существующее объявление класса, чтобы он имел следующее имя и наследовался от элемента <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### Инициализация элемента управления  
 Следующий код реализует несколько основных задач.  
  
-   Объявляет частное событие `OnButtonClick` и его связанный делегат `MyControlEventHandler`.  
  
-   Создает несколько частных глобальных переменных, хранящих данные пользователя.  Эти данные предоставляются через соответствующие свойства.  
  
-   Реализует обработчик `Init` для события <xref:System.Windows.FrameworkElement.Loaded> элемента управления.  Этот обработчик инициализирует глобальные переменные путем назначения их значений, определенных в файле MyControl1.xaml.  Для этого он использует свойство <xref:System.Windows.FrameworkElement.Name%2A>, назначенное типичному элементу <xref:System.Windows.Controls.TextBlock> `nameLabel`, для доступа к параметрам свойств этого элемента.  
  
 Удалите существующий конструктор и добавьте следующий код в класс `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### Обработка событий нажатия кнопки  
 Пользователь указывает, что задача ввода данных завершена, нажав кнопку **OK** или **Cancel**.  Обе кнопки используют тот же обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> — `ButtonClicked`.  Обе кнопки имеют имя `btnOK` или `btnCancel`, которое позволяет обработчику определить, какая кнопка была нажата, путем проверки значения аргумента `sender`.  Обработчик выполняет следующие действия.  
  
-   Создает объект `MyControlEventArgs`, содержащий данные из элементов <xref:System.Windows.Controls.TextBox>.  
  
-   Если пользователь нажимает кнопку **Отмена**, для свойства `IsOK` объекта `MyControlEventArgs` задает значение `false`.  
  
-   Вызывает событие `OnButtonClick`, чтобы указать узлу, что пользователь завершил работу, и передает обратно собранные данные.  
  
 Добавьте следующий код в класс `MyControl1` после метода `Init`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### Создание свойств  
 Оставшаяся часть класса просто предоставляет свойства, которые соответствуют описанным выше глобальным переменным.  При изменении свойства метод доступа set изменяет внешний вид элемента управления путем изменения соответствующих свойств элемента и обновления базовых глобальных переменных.  
  
 Добавьте следующий код к классу `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### Отправка данных обратно на узел  
 Завершающим компонентом в файле является класс `MyControlEventArgs`, который используется для отправки собранных данных обратно на узел.  
  
 Добавьте следующий код к пространству имен `MyControls`.  Реализация является простой и далее не рассматривается.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Выполните построение решения.  Построение создаст DLL с именем MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## Реализация ведущего приложения Windows Forms  
 Для размещения составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в ведущем приложении [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] используется объект <xref:System.Windows.Forms.Integration.ElementHost>.  Приложение обрабатывает событие `OnButtonClick` для получения данных из составного элемента управления.  Приложение также содержит набор переключателей, которые можно использовать для изменения внешнего вида элемента управления.  На следующем рисунке показано приложение.  
  
 ![Элемент управления Avalon, размещаемый Windows Forms](../../../../docs/framework/wpf/advanced/media/wfhost.png "WFHost")  
Составной элемент управления WPF в приложении Windows Forms  
  
### Создание проекта  
 Для запуска проекта выполните следующие действия.  
  
1.  Запустите среду [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] и откройте диалоговое окно **Новый проект**.  
  
2.  В Visual C\# и категории Windows выберите шаблон **Приложение Windows Forms**.  
  
3.  Присвойте проекту имя `WFHost`.  
  
4.  В качестве расположение укажите ту же папку верхнего уровня, в которой содержится проект MyControls.  
  
5.  Нажмите кнопку **ОК**, чтобы создать проект.  
  
 Также необходимо добавить ссылки на библиотеку DLL, содержащую элемент управления `MyControl1` и другие сборки.  
  
1.  Щелкните правой кнопкой мыши имя проекта в обозревателе решений и выберите команду **Добавить ссылку**.  
  
2.  Перейдите на вкладку **Обзор** и укажите папку, которая содержит файл MyControls.dll.  В данном пошаговом руководстве это папка MyControls\\bin\\Debug.  
  
3.  Выберите файл MyControls.dll и нажмите кнопку **ОК**.  
  
4.  Добавьте ссылки на следующие сборки:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   System.Xaml  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
### Реализация пользовательского интерфейса для приложения  
 Пользовательский интерфейс приложения Windows Form содержит несколько элементов управления для взаимодействия с составным элементом управления WPF.  
  
1.  Откройте приложение Form1 в конструкторе Windows Form.  
  
2.  Увеличьте форму, чтобы разместить элементы управления.  
  
3.  Добавьте элемент управления <xref:System.Windows.Forms.Panel?displayProperty=fullName> в правый верхний угол формы для размещения составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
4.  Добавьте в форму следующие элементы управления <xref:System.Windows.Forms.GroupBox?displayProperty=fullName>.  
  
    |Имя|Текст|  
    |---------|-----------|  
    |groupBox1|Цвет фона|  
    |groupBox2|Цвет шрифта|  
    |groupBox3|Font Size|  
    |groupBox4|Семейство шрифтов|  
    |groupBox5|Стиль шрифта|  
    |groupBox6|Насыщенность шрифта|  
    |groupBox7|Данные из элемента управления|  
  
5.  Добавьте в элементы управления <xref:System.Windows.Forms.GroupBox?displayProperty=fullName> следующие элементы управления <xref:System.Windows.Forms.RadioButton?displayProperty=fullName>.  
  
    |GroupBox|Имя|Текст|  
    |--------------|---------|-----------|  
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
    |groupBox4|radioFamilyTimes|Times New Roman|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|Обычные|  
    |groupBox5|radioStyleItalic|Курсив|  
    |groupBox6|radioWeightOriginal|До преобразования|  
    |groupBox6|radioWeightBold|Полужирный|  
  
6.  Добавьте в последний элемент управления <xref:System.Windows.Forms.GroupBox?displayProperty=fullName> следующие элементы управления <xref:System.Windows.Forms.Label?displayProperty=fullName>.  Эти элементы управления отображают данные, возвращенные составным элементом управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    |GroupBox|Имя|Текст|  
    |--------------|---------|-----------|  
    |groupBox7|lblName|Имя:|  
    |groupBox7|lblAddress|Street Address:|  
    |groupBox7|lblCity|City:|  
    |groupBox7|lblState|State:|  
    |groupBox7|lblZip|Zip:|  
  
### Инициализация формы  
 Код размещения обычно реализуется в обработчике событий <xref:System.Windows.Forms.Form.Load> формы.  В следующем коде показан обработчик событий <xref:System.Windows.Forms.Form.Load>, обработчик событий <xref:System.Windows.FrameworkElement.Loaded> составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и объявления нескольких глобальных переменных, которые будут использованы позже.  
  
 В конструкторе Windows Forms дважды щелкните форму, чтобы создать обработчик событий <xref:System.Windows.Forms.Form.Load>.  В начале файла Form1.cs добавьте следующие операторы `using`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Замените содержимое существующего класса `Form1` следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Метод `Form1_Load` в предыдущем коде показывает общую процедуру размещения элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
1.  Создайте новый объект <xref:System.Windows.Forms.Integration.ElementHost>.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> элемента управления значение <xref:System.Windows.Forms.DockStyle?displayProperty=fullName>.  
  
3.  Добавьте элемент управления <xref:System.Windows.Forms.Integration.ElementHost> к коллекции <xref:System.Windows.Forms.Control.Controls%2A> элементов управления <xref:System.Windows.Forms.Panel>.  
  
4.  Создайте экземпляр элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
5.  Разместите составной элемент управления в форме путем назначения элемента управления свойству <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
 Остальные две строки в методе `Form1_Load` присоединяют обработчики к двум событиям элемента управления:  
  
-   `OnButtonClick` — пользовательское событие, создаваемое составным элементом управления при нажатии кнопки **OK** или **Cancel**.  Обработайте событие для получения ответа пользователя и сбора всех введенных им данных.  
  
-   <xref:System.Windows.FrameworkElement.Loaded> — стандартное событие, которое вызывается элементом управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], когда он полностью загружен.  Это событие используется здесь потому, что для примера необходима инициализация нескольких глобальных переменных свойствами элемента управления.  Во время события <xref:System.Windows.Forms.Form.Load> формы элемент управления не полностью загружен, и для этих переменных по\-прежнему задается значение `null`.  Прежде чем получить доступ к этим свойствам, необходимо дождаться события <xref:System.Windows.FrameworkElement.Loaded> элемента управления.  
  
 Обработчик событий <xref:System.Windows.FrameworkElement.Loaded> показан в предыдущем коде.  Обработчик `OnButtonClick` рассматривается в следующем разделе.  
  
### Обработка события OnButtonClick  
 Событие `OnButtonClick` происходит, когда пользователь нажимает кнопку **ОК** или **Отмена**.  
  
 Обработчик событий проверяет поле `IsOK` аргумента события, чтобы определить, какая кнопка была нажата.  Переменные `lbl`*data* соответствуют элементам управления <xref:System.Windows.Forms.Label>, которые были описаны выше.  Если пользователь нажимает кнопку **ОК**, данные из элементов управления <xref:System.Windows.Controls.TextBox> элемента управления назначаются соответствующему элементу управления <xref:System.Windows.Forms.Label>.  Если пользователь нажимает кнопку **Cancel**, для свойств <xref:System.Windows.Forms.Label.Text%2A> устанавливаются строки по умолчанию.  
  
 Добавьте следующий код обработчика событий нажатия кнопки в класс `Form1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Постройте и запустите приложение.  Добавьте произвольный текст в составной элемент управления WPF и нажмите кнопку **OK**.  Этот текст появится в подписях.  На данном этапе код для обработки переключателей еще не добавлен.  
  
### Изменение внешнего вида элемента управления  
 Элементы управления <xref:System.Windows.Forms.RadioButton> формы позволяют пользователю изменять цвет шрифта и фона составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а также ряд свойств шрифта.  Цвет фона предоставляется объектом <xref:System.Windows.Forms.Integration.ElementHost>.  Остальные свойства предоставляются как настраиваемые свойства элемента управления.  
  
 Дважды щелкните каждый элемент управления <xref:System.Windows.Forms.RadioButton> в форме, чтобы создать обработчики событий <xref:System.Windows.Forms.RadioButton.CheckedChanged>.  Замените обработчики событий <xref:System.Windows.Forms.RadioButton.CheckedChanged> следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Постройте и запустите приложение.  Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в составном элементе управления WPF.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)