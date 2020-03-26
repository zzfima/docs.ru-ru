---
title: Размещение композитного управления WPF в формах Windows
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: 88efab8adf36989938ba5aa887a28b41eb8820f3
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291623"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако, когда у вас есть значительные инвестиции в код Windows Forms, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] может быть более эффективным расширить существующее приложение Windows Forms, а не переписывать его с нуля. Распространенным сценарием является встраиваемый [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] один или несколько элементов управления, реализованных в приложении Windows Forms. Для получения дополнительной информации о [Control Customization](../controls/control-customization.md)настройке элементов управления WPF см.  
  
 Это пошаговое окно проходит [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] через приложение, в котором размещается композитный элемент управления для выполнения ввода данных в приложении Windows Forms. Составной элемент управления упакован в библиотеку DLL. Эта общая процедура может быть расширена для более сложных приложений и элементов управления. Это пошаговое походе предназначено для почти идентичны хиножа по внешнему виду и функциональности [Для Walkthrough: Хостинг композитного управления Windows Forms в WPF.](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md) Основным отличием является то, что сценарий размещения выполняется в обратном порядке.  
  
 Пошаговое руководство состоит из двух разделов. В первом разделе кратко описывается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализация композитного управления. Во втором разделе подробно рассказывается о том, как разместить композитный элемент управления в приложении Windows Forms, получать события из элемента управления и получать доступ к некоторым свойствам элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
- Реализация составного элемента управления WPF  
  
- Реализация ведущего приложения Windows Forms  
  
 Полный список задач, иллюстрированных в этом пошаговом шаге, можно узнать в [примере форм Windows.](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl)  
  
## <a name="prerequisites"></a>Предварительные требования  

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.  
  
## <a name="implementing-the-wpf-composite-control"></a>Реализация составного элемента управления WPF  
 Композитный [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент управления, используемый в этом примере, представляет собой простую форму входа данных, которая принимает имя и адрес пользователя. Когда пользователь нажимает одну из двух кнопок, чтобы указать, что задача завершена, элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение. На приведенном ниже рисунке показан отображаемый элемент управления.

 На следующем изображении показан композитный контроль WPF:

 ![Скриншот, который показывает простой контроль WPF.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1. Запустите Visual Studio и откройте диалоговую коробку **нового проекта.**  
  
2. В категории Visual C и Windows выберите шаблон **библиотеки управления пользователями WPF.**  
  
3. Присвойте проекту имя `MyControls`.  
  
4. Для определения местоположения укажите удобно названную папку `WindowsFormsHostingWpfControl`верхнего уровня, например. Позже ведущее приложение будет помещено в эту папку.  
  
5. Нажмите кнопку **ОК**, чтобы создать проект. Проект по умолчанию содержит `UserControl1`один элемент управления с именем .  
  
6. В Solution Explorer `UserControl1` переименуем в `MyControl1`.  
  
 Проект должен иметь ссылки на перечисленные ниже системные библиотеки DLL. Если какие-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.  
  
- PresentationCore  
  
- PresentationFramework  
  
- Система  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Создание пользовательского интерфейса  
 Композитный [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] элемент управления реализован [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]с помощью . Композитный [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемент состоит <xref:System.Windows.Controls.TextBox> из пяти элементов. Каждый <xref:System.Windows.Controls.TextBox> элемент <xref:System.Windows.Controls.TextBlock> имеет связанный элемент, который служит меткой. Есть два <xref:System.Windows.Controls.Button> элемента в нижней части, **OK** и **Отменить**. При нажатии любой кнопки элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение.  
  
#### <a name="basic-layout"></a>Базовый макет  
 Различные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы содержатся в элементе. <xref:System.Windows.Controls.Grid> Можно использовать <xref:System.Windows.Controls.Grid> для организации содержимого элемента управления во многом `Table` таким же образом, как вы бы использовали элемент в HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также имеет <xref:System.Windows.Documents.Table> элемент, <xref:System.Windows.Controls.Grid> но более легкий и лучше подходит для простых задач макета.  
  
 В приведенном ниже коде XAML показан базовый макет. Этот XAML определяет общую структуру элемента, определяя количество <xref:System.Windows.Controls.Grid> столбцов и строк в элементе.  
  
 В файле MyControl1.xaml замените имеющийся код XAML приведенным ниже кодом.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Добавление в сетку элементов TextBlock и TextBox  
 Элемент в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] сетке размещается, устанавливая элемент <xref:System.Windows.Controls.Grid.RowProperty> и <xref:System.Windows.Controls.Grid.ColumnProperty> атрибуты на соответствующий номер строки и столбца. Следует помнить, что нумерация строк и столбцов ведется от нуля. Элемент может охватывать несколько столбцов, <xref:System.Windows.Controls.Grid.ColumnSpanProperty> установив его атрибут. Для получения <xref:System.Windows.Controls.Grid> дополнительной информации об элементах см. [Create a Grid Element](../controls/how-to-create-a-grid-element.md)  
  
 Следующие XAML показывает композитный <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBlock> элемент управления <xref:System.Windows.Controls.Grid.RowProperty> <xref:System.Windows.Controls.Grid.ColumnProperty> и элементы с их и атрибуты, которые установлены для размещения элементов должным образом в сетке.  
  
 В MyControl1.xaml добавьте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Создание стилей элементов пользовательского интерфейса  
 Многие элементы в форме для ввода данных имеют одинаковый внешний вид. Это означает, что они имеют одинаковые значения нескольких свойств. Вместо того, чтобы устанавливать атрибуты каждого элемента <xref:System.Windows.Style> отдельно, предыдущий XAML использует элементы для определения стандартных параметров свойств для классов элементов. Такой подход упрощает элемент управления и позволяет изменять внешний вид нескольких элементов посредством одного атрибута стиля.  
  
 Элементы <xref:System.Windows.Style> содержатся <xref:System.Windows.Controls.Grid> в свойстве элемента, <xref:System.Windows.FrameworkElement.Resources%2A> поэтому они могут быть использованы всеми элементами в элементе управления. Если стиль назван, вы применяйте его <xref:System.Windows.Style> к элементу, добавляя элемент, установленный к имени стиля. Неименованные стили становятся стилями по умолчанию для элемента. Для получения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] дополнительной информации о стилях, [см Стиль и Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
 Следующие XAML <xref:System.Windows.Style> показывает элементы для композитного управления. Чтобы увидеть, как стили применяются к элементам, см. предыдущий код XAML. Например, последний <xref:System.Windows.Controls.TextBlock> элемент `inlineText` имеет стиль, <xref:System.Windows.Controls.TextBox> а последний элемент использует стиль по умолчанию.  
  
 В MyControl1.xaml добавьте следующий XAML сразу после начала элемента. <xref:System.Windows.Controls.Grid>  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Добавление кнопок OK и "Отмена"  
 Окончательными элементами композитного управления являются элементы **OK** и **Cancel,** <xref:System.Windows.Controls.Button> которые занимают <xref:System.Windows.Controls.Grid>первые две колонны последнего ряда . Эти элементы используют общий обработчик событий и стиль по умолчанию, `ButtonClicked` <xref:System.Windows.Controls.Button> определенный в предыдущем XAML.  
  
 В MyControl1.xaml добавьте следующий XAML после последнего <xref:System.Windows.Controls.TextBox> элемента. Часть [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] композитного управления завершена.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Реализация файла кода программной части  
 Файл за кодом, MyControl1.xaml.cs, реализует три основные задачи:
  
1. обрабатывает событие, когда пользователь нажимает одну из кнопок;  
  
2. Извлекает данные <xref:System.Windows.Controls.TextBox> из элементов и упаковывает их в объект аргумента пользовательского события.  
  
3. Поднимает пользовательское `OnButtonClick` событие, которое уведомляет узел о завершении пользователя и передает данные хосту.  
  
 Элемент управления также предоставляет ряд свойств цвета и шрифтов, которые позволяют изменять внешний вид. В <xref:System.Windows.Forms.Integration.WindowsFormsHost> отличие от класса, который используется для <xref:System.Windows.Forms.Integration.ElementHost> размещения управления формами <xref:System.Windows.Controls.Panel.Background%2A> Windows, класс предоставляет только свойство элемента управления. Для поддержания сходства между этим примером кода и примером, обсуждаемым в [Walkthrough: Hosting a Windows Forms Composite Control в WPF,](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)элемент управления предоставляет оставшиеся свойства напрямую.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Базовая структура файла кода программной части  
 Файл с кодом состоит из одного `MyControls`пространства имен, которое будет содержать два класса, `MyControl1` и `MyControlEventArgs`.  
  
```csharp  
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
  
 Первый класс, это частичный класс, `MyControl1`содержащий код, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] который реализует функциональность определенного в MyControl1.xaml. При разборе MyControl1.xaml [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] преобразуется в один и тот же частичный класс, и два частичных класса объединяются в состав компилированного элемента управления. По этой причине имя класса в файле кода программной части должно совпадать с именем класса, назначенным в файле MyControl1.xaml, и наследоваться от корневого элемента управления. Второй класс `MyControlEventArgs`— это класс аргументов событий, который используется для отправки данных обратно униза.  
  
 Откройте файл MyControl1.xaml.cs. Измените существующую декларацию класса так, чтобы <xref:System.Windows.Controls.Grid>она получила следующее название и унаследовала от .  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Инициализация элемента управления  
 Приведенный ниже код реализует несколько основных задач:  
  
- Объявляет частное мероприятие, `OnButtonClick`и связанный `MyControlEventHandler`с ним делегат, .  
  
- создает несколько частных глобальных переменных, хранящих данные пользователя. Эти данные предоставляются через соответствующие свойства;  
  
- Реализует обработчик, `Init`для события <xref:System.Windows.FrameworkElement.Loaded> элемента управления. Этот обработчик инициализирует глобальные переменные путем присвоения им значений, определенных в файле MyControl1.xaml. Для этого он использует <xref:System.Windows.FrameworkElement.Name%2A> назначенный для <xref:System.Windows.Controls.TextBlock> типичного `nameLabel`элемента, чтобы получить доступ к настройкам свойства этого элемента.  
  
 Удалите существующий конструктор и добавьте следующий код в свой `MyControl1` класс.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Обработка событий нажатия кнопки  
 Пользователь указывает, что задача ввода данных завершена, нажав либо кнопку **OK,** либо кнопку **«Отмена».** Обе кнопки используют <xref:System.Windows.Controls.Primitives.ButtonBase.Click> один `ButtonClicked`и тот же обработчик событий. Обе кнопки имеют `btnOK` имя, или `btnCancel`, что позволяет обработчику определить, `sender` какая кнопка была нажата, изучая значение аргумента. Обработчик выполняет следующие действия:  
  
- Создает `MyControlEventArgs` объект, содержащий данные <xref:System.Windows.Controls.TextBox> из элементов.  
  
- Если пользователь нажал кнопку **Отмена,** успокоите свойство `MyControlEventArgs` `IsOK` объекта. `false`  
  
- Поднимает `OnButtonClick` событие, чтобы указать хосту, что пользователь закончил, и передает обратно собранные данные.  
  
 Добавьте следующий `MyControl1` код в `Init` свой класс после метода.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Создание свойств  
 Оставшаяся часть класса просто предоставляет свойства, которые соответствуют описанным выше глобальным переменным. При изменении свойства метод доступа set изменяет внешний вид элемента управления путем изменения соответствующих свойств элемента и обновления базовых глобальных переменных.  
  
 Добавьте следующий `MyControl1` код в свой класс.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Отправка данных обратно в ведущее приложение  
 Окончательным компонентом в `MyControlEventArgs` файле является класс, который используется для отправки собранных данных обратно в универса.  
  
 Добавьте следующий `MyControls` код в пространство имен. Реализация является простой и далее не рассматривается.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Создайте решение. Сборка создаст библиотеку DLL с именем MyControls.dll.  
  
<a name="winforms_host_section"></a>
## <a name="implementing-the-windows-forms-host-application"></a>Реализация ведущего приложения Windows Forms  
 Хост-приложение Windows <xref:System.Windows.Forms.Integration.ElementHost> Forms использует [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объект для размещения композитного элемента управления. Приложение обрабатывает `OnButtonClick` событие для получения данных из композитного элемента управления. Приложение также имеет набор кнопок опции, которые можно использовать для изменения внешнего вида управления. На рисунке ниже показано приложение.  

Следующее изображение показывает композитный элемент управления WPF, размещенный в приложении Windows Forms"  

 ![Скриншот, который показывает Windows Form Hosting Avalon управления.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1. Запустите Visual Studio и откройте диалоговую коробку **нового проекта.**  
  
2. В категории Visual C и Windows выберите шаблон **приложения Windows Forms.**  
  
3. Присвойте проекту имя `WFHost`.  
  
4. В качестве расположения укажите ту же папку верхнего уровня, в которой содержится проект MyControls.  
  
5. Нажмите кнопку **ОК**, чтобы создать проект.  
  
 Также необходимо добавить ссылки на DLL, содержащий `MyControl1` и другие сборки.  
  
1. Нажмите правой кнопкой мыши название проекта в Solution Explorer и выберите **Добавить справку.**  
  
2. Нажмите на вкладку **«Просмотр»** и просмотрите папку MyControls.dll. В данном пошаговом руководстве это папка MyControls\bin\Debug.  
  
3. Выберите MyControls.dll, а затем нажмите **OK**.  
  
4. Добавьте ссылки на следующие сборки.  
  
    - PresentationCore  
  
    - PresentationFramework  
  
    - System.Xaml  
  
    - WindowsBase  
  
    - WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>Реализация пользовательского интерфейса для приложения  
 Пользовательский интерфейс приложения Windows Forms содержит несколько элементов управления для взаимодействия с составным элементом управления WPF.  
  
1. Откройте приложение Form1 в конструкторе Windows Forms.  
  
2. Увеличьте форму, чтобы разместить элементы управления.  
  
3. В верхнем правом углу формы добавьте <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления, чтобы удерживать композитный контроль.  
  
4. Добавьте <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> в форму следующие элементы управления.  
  
    |name|текст|  
    |----------|----------|  
    |groupBox1|Цвет фона|  
    |groupBox2|Цвет переднего плана|  
    |groupBox3|Размер шрифта|  
    |groupBox4|Семейство шрифтов|  
    |groupBox5|Стиль шрифта|  
    |groupBox6|Насыщенность шрифта|  
    |groupBox7|Данные из элемента управления|  
  
5. Добавьте <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> в элементы <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> управления следующие элементы управления.  
  
    |GroupBox|name|текст|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Исходное значение|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|Исходное значение|  
    |groupBox2|radioForegroundRed|Красный|  
    |groupBox2|radioForegroundYellow|Желтый|  
    |groupBox3|radioSizeOriginal|Исходное значение|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|Исходное значение|  
    |groupBox4|radioFamilyTimes|Times New Roman Cyr|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|Нормальный|  
    |groupBox5|radioStyleItalic|Italic|  
    |groupBox6|radioWeightOriginal|Исходное значение|  
    |groupBox6|radioWeightBold|Полужирный|  
  
6. Добавьте <xref:System.Windows.Forms.Label?displayProperty=nameWithType> следующие элементы управления к последнему <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>. Эти элементы управления отображают данные, возвращенные композитным управлением. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
    |GroupBox|name|текст|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Имя:|  
    |groupBox7|lblAddress|Почтовый адрес:|  
    |groupBox7|lblCity|Город:|  
    |groupBox7|lblState|Состояние:|  
    |groupBox7|lblZip|Почтовый индекс:|  
  
### <a name="initializing-the-form"></a>Инициализация формы  
 Обычно код хостинга реализуется в <xref:System.Windows.Forms.Form.Load> обработчике событий в форме. Следующий код <xref:System.Windows.Forms.Form.Load> показывает обработчик событий, обработчик для события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] композитного элемента <xref:System.Windows.FrameworkElement.Loaded> управления и декларации для нескольких глобальных переменных, которые используются позже.  
  
 В конструкторе форм Windows дважды щелкните форму для создания обработчика <xref:System.Windows.Forms.Form.Load> событий. В верхней части Form1.cs `using` добавьте следующие заявления.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Замените содержимое `Form1` существующего класса следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Метод `Form1_Load` в предыдущем коде показывает общую [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] процедуру размещения элемента управления:  
  
1. Создайте объект <xref:System.Windows.Forms.Integration.ElementHost>.  
  
2. Установите свойство <xref:System.Windows.Forms.Control.Dock%2A> управления. <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>  
  
3. Добавьте <xref:System.Windows.Forms.Integration.ElementHost> элемент <xref:System.Windows.Forms.Panel> управления в <xref:System.Windows.Forms.Control.Controls%2A> коллекцию управления.  
  
4. Создайте экземпляр [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемента управления.  
  
5. Размещайте композитный элемент управления в форме, назначая элемент управления свойству <xref:System.Windows.Forms.Integration.ElementHost> элемента <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> управления.  
  
 Остальные две строки `Form1_Load` метода прикрепляют обработчики к двум контрольным событиям:  
  
- `OnButtonClick`это пользовательское событие, которое выражается композитным управлением, когда пользователь нажимает кнопку **OK** или **Cancel.** Обработайте событие для получения ответа пользователя и сбора всех введенных им данных.  
  
- <xref:System.Windows.FrameworkElement.Loaded>является стандартным событием, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] которое возникает элементом управления при полной загрузке. Это событие используется здесь потому, что для примера необходима инициализация нескольких глобальных переменных свойствами элемента управления. Во время <xref:System.Windows.Forms.Form.Load> события формы элемент управления не полностью загружен, и эти значения `null`по-прежнему настроены на . Вам нужно подождать, пока <xref:System.Windows.FrameworkElement.Loaded> событие элемента управления произойдет, прежде чем вы сможете получить доступ к этим свойствам.  
  
 Обработчик <xref:System.Windows.FrameworkElement.Loaded> событий отображается в предыдущем коде. Обработчик `OnButtonClick` обсуждается в следующем разделе.  
  
### <a name="handling-onbuttonclick"></a>Обработка события OnButtonClick  
 Событие `OnButtonClick` происходит, когда пользователь нажимает кнопку **OK** или **Cancel.**  
  
 Обработчик события проверяет поле `IsOK` аргумента события, чтобы определить, какая кнопка была нажата. Переменные `lbl` *данных* соответствуют <xref:System.Windows.Forms.Label> элементам управления, которые обсуждались ранее. Если пользователь нажимает кнопку **OK,** данные из элементов <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Forms.Label> управления назначаются соответствующему управлению. Если пользователь нажимает <xref:System.Windows.Forms.Label.Text%2A> **На кнопку Cancel,** значения устанавливаются на строки по умолчанию.  
  
 Добавьте в класс следующий `Form1` код обработчика событий кнопки кнопки нажмите кнопку.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Выполните сборку и запустите приложение. Добавьте текст в композитный элемент управления WPF, а затем нажмите **OK.** Этот текст появится в метках. На данном этапе код для обработки переключателей еще не добавлен.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Изменение внешнего вида элемента управления  
 Элементы <xref:System.Windows.Forms.RadioButton> управления в форме позволят пользователю изменить передний план и фоновые цвета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемента управления, а также несколько свойств шрифта. Цвет фона подвергается <xref:System.Windows.Forms.Integration.ElementHost> объекту. Остальные свойства предоставляются как настраиваемые свойства элемента управления.  
  
 Для создания <xref:System.Windows.Forms.RadioButton.CheckedChanged> <xref:System.Windows.Forms.RadioButton> обработчиков событий дважды щелкните каждый элемент управления в форме. Замените <xref:System.Windows.Forms.RadioButton.CheckedChanged> обработчики событий следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Выполните сборку и запустите приложение. Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в составном элементе управления WPF.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговая прогулка: Хостинг 3D Композитный контроль WPF в формах Windows](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
