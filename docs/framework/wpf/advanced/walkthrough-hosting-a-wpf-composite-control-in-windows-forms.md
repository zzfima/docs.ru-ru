---
title: Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: 0054ac49589991d754da655e9f8f52d63e9a6274
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920224"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако при наличии значительных инвестиций в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] код может оказаться более эффективным, чтобы расширить имеющееся приложение [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а не переписывать его с нуля. Распространенный сценарий заключается в том, что необходимо внедрить один или несколько элементов управления, реализованных с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в приложении Windows Forms. Дополнительные сведения о настройке элементов управления WPF см. в разделе [Настройка элемента управления](../controls/control-customization.md).  
  
 В этом пошаговом руководстве рассматривается приложение, в котором размещается [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составной элемент управления для выполнения записи данных в Windows Forms приложении. Составной элемент управления упакован в библиотеку DLL. Эта общая процедура может быть расширена для более сложных приложений и элементов управления. Это пошаговое руководство призвано стать практически идентичным по внешнему виду и функциональности для [пошагового руководства: размещение Windows Forms составного элемента управления в WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md). Основным отличием является то, что сценарий размещения выполняется в обратном порядке.  
  
 Пошаговое руководство состоит из двух разделов. В первом разделе кратко описывается реализация составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Во втором разделе подробно рассматривается размещение составного элемента управления в Windows Forms приложении, получение событий из элемента управления и доступ к некоторым свойствам элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
- Реализация составного элемента управления WPF  
  
- Реализация ведущего приложения Windows Forms  
  
 Полный листинг кода задач, показанных в этом пошаговом руководстве, см. [в разделе размещение составного элемента управления WPF в Windows Forms примере](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl).  
  
## <a name="prerequisites"></a>Необходимые компоненты  

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.  
  
## <a name="implementing-the-wpf-composite-control"></a>Реализация составного элемента управления WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составной элемент управления, используемый в этом примере, представляет собой простую форму ввода данных, которая принимает имя пользователя и адрес. Когда пользователь нажимает одну из двух кнопок, чтобы указать, что задача завершена, элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение. На приведенном ниже рисунке показан отображаемый элемент управления. 

 На следующем рисунке показан составной элемент управления WPF: 

 ![Снимок экрана, на котором показан простой элемент управления WPF.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1. Запустите Visual Studio и откройте диалоговое окно **Создание проекта** .  
  
2. В области C# визуальные элементы и Категория Windows выберите шаблон **Библиотека пользовательского элемента управления WPF** .  
  
3. Присвойте проекту имя `MyControls`.  
  
4. В качестве расположения укажите папку верхнего уровня с удобным именем, например `WindowsFormsHostingWpfControl`. Позже ведущее приложение будет помещено в эту папку.  
  
5. Нажмите кнопку **ОК**, чтобы создать проект. Проект по умолчанию содержит один элемент управления с именем `UserControl1`.  
  
6. В обозреватель решений переименуйте `UserControl1` в `MyControl1`.  
  
 Проект должен иметь ссылки на перечисленные ниже системные библиотеки DLL. Если какие-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.  
  
- PresentationCore  
  
- PresentationFramework  
  
- Система  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Создание пользовательского интерфейса  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] составного элемента управления реализуется с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Составной элемент управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] состоит из пяти элементов <xref:System.Windows.Controls.TextBox>. Каждый элемент <xref:System.Windows.Controls.TextBox> имеет связанный элемент <xref:System.Windows.Controls.TextBlock>, который служит меткой. Внизу есть два элемента <xref:System.Windows.Controls.Button>, **ОК** и **Отмена**. При нажатии любой кнопки элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение.  
  
#### <a name="basic-layout"></a>Базовый макет  
 Различные элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] содержатся в элементе <xref:System.Windows.Controls.Grid>. <xref:System.Windows.Controls.Grid> можно использовать для упорядочения содержимого составного элемента управления практически так же, как элемент `Table` в HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также имеет элемент <xref:System.Windows.Documents.Table>, но <xref:System.Windows.Controls.Grid> более упрощен и лучше подходит для простых задач макета.  
  
 В приведенном ниже коде XAML показан базовый макет. Этот XAML определяет общую структуру элемента управления, указывая количество столбцов и строк в элементе <xref:System.Windows.Controls.Grid>.  
  
 В файле MyControl1.xaml замените имеющийся код XAML приведенным ниже кодом.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Добавление в сетку элементов TextBlock и TextBox  
 Элемент [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] помещается в сетку путем установки атрибутов <xref:System.Windows.Controls.Grid.RowProperty> и <xref:System.Windows.Controls.Grid.ColumnProperty> элемента в соответствующие номера строк и столбцов. Следует помнить, что нумерация строк и столбцов ведется от нуля. Элемент может охватывать несколько столбцов путем установки его атрибута <xref:System.Windows.Controls.Grid.ColumnSpanProperty>. Дополнительные сведения об элементах <xref:System.Windows.Controls.Grid> см. [в разделе Создание элемента Grid](../controls/how-to-create-a-grid-element.md).  
  
 В следующем коде XAML показаны элементы <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.TextBlock> составного элемента управления с их <xref:System.Windows.Controls.Grid.RowProperty> и <xref:System.Windows.Controls.Grid.ColumnProperty> атрибутами, которые устанавливаются для правильного размещения элементов в сетке.  
  
 В файле MyControl1. XAML добавьте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Создание стилей элементов пользовательского интерфейса  
 Многие элементы в форме для ввода данных имеют одинаковый внешний вид. Это означает, что они имеют одинаковые значения нескольких свойств. Вместо того чтобы задавать атрибуты каждого элемента отдельно, предыдущий XAML использует <xref:System.Windows.Style> элементы для определения стандартных настроек свойств для классов элементов. Такой подход упрощает элемент управления и позволяет изменять внешний вид нескольких элементов посредством одного атрибута стиля.  
  
 Элементы <xref:System.Windows.Style> содержатся в свойстве <xref:System.Windows.FrameworkElement.Resources%2A> элемента <xref:System.Windows.Controls.Grid>, поэтому они могут использоваться всеми элементами в элементе управления. Если стиль называется, его можно применить к элементу, добавив элемент <xref:System.Windows.Style>, которому присвоено имя стиля. Неименованные стили становятся стилями по умолчанию для элемента. Дополнительные сведения о стилях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Стилизация и создание шаблонов](../controls/styling-and-templating.md).  
  
 В следующем коде XAML показаны элементы <xref:System.Windows.Style> для составного элемента управления. Чтобы увидеть, как стили применяются к элементам, см. предыдущий код XAML. Например, последний элемент <xref:System.Windows.Controls.TextBlock> имеет стиль `inlineText`, а последний элемент <xref:System.Windows.Controls.TextBox> использует стиль по умолчанию.  
  
 В файле MyControl1. XAML добавьте следующий код XAML сразу после начального элемента <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Добавление кнопок OK и "Отмена"  
 Последними элементами в составном элементе управления являются элементы **ОК** и **Отмена**<xref:System.Windows.Controls.Button>, которые занимают первые два столбца последней строки <xref:System.Windows.Controls.Grid>. Эти элементы используют общий обработчик событий, `ButtonClicked`и стиль <xref:System.Windows.Controls.Button> по умолчанию, определенный в предыдущем XAML.  
  
 В файле MyControl1. XAML добавьте следующий код XAML после последнего элемента <xref:System.Windows.Controls.TextBox>. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] часть составного элемента управления теперь завершена.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Реализация файла кода программной части  
 Файл кода программной части, MyControl1.xaml.cs, реализует три критических задачи:
  
1. обрабатывает событие, когда пользователь нажимает одну из кнопок;  
  
2. Извлекает данные из элементов <xref:System.Windows.Controls.TextBox> и упаковывает их в объект аргумента пользовательского события.  
  
3. Вызывает событие пользовательского `OnButtonClick`, которое уведомляет узел о завершении работы пользователя и передает данные на узел.  
  
 Элемент управления также предоставляет ряд свойств цвета и шрифтов, которые позволяют изменять внешний вид. В отличие от класса <xref:System.Windows.Forms.Integration.WindowsFormsHost>, который используется для размещения элемента управления Windows Forms, класс <xref:System.Windows.Forms.Integration.ElementHost> предоставляет только свойство <xref:System.Windows.Controls.Panel.Background%2A> элемента управления. Чтобы сохранить сходство между этим примером кода и примером, описанным в [разделе Пошаговое руководство. размещение составного элемента управления Windows Forms в WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), элемент управления предоставляет оставшиеся свойства напрямую.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Базовая структура файла кода программной части  
 Файл кода программной части состоит из одного пространства имен `MyControls`, которое будет содержать два класса: `MyControl1` и `MyControlEventArgs`.  
  
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
  
 Первый класс, `MyControl1`, является разделяемым классом, содержащим код, реализующий функциональные возможности [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] определенного в файле MyControl1. XAML. При синтаксическом анализе файле MyControl1. XAML [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] преобразуется в тот же разделяемый класс, а два разделяемых класса объединяются для формирования скомпилированного элемента управления. По этой причине имя класса в файле кода программной части должно совпадать с именем класса, назначенным в файле MyControl1.xaml, и наследоваться от корневого элемента управления. Второй класс, `MyControlEventArgs`, является классом аргументов события, который используется для отправки данных на узел.  
  
 Откройте файл MyControl1.xaml.cs. Измените существующее объявление класса так, чтобы оно собыло следующее имя и наследовало от <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Инициализация элемента управления  
 Приведенный ниже код реализует несколько основных задач:  
  
- Объявляет закрытое событие, `OnButtonClick`и связанный с ним делегат `MyControlEventHandler`.  
  
- создает несколько частных глобальных переменных, хранящих данные пользователя. Эти данные предоставляются через соответствующие свойства;  
  
- Реализует обработчик `Init`для события <xref:System.Windows.FrameworkElement.Loaded> элемента управления. Этот обработчик инициализирует глобальные переменные путем присвоения им значений, определенных в файле MyControl1.xaml. Для этого он использует <xref:System.Windows.FrameworkElement.Name%2A>, назначенный обычному элементу <xref:System.Windows.Controls.TextBlock>, `nameLabel`, чтобы получить доступ к параметрам свойства этого элемента.  
  
 Удалите существующий конструктор и добавьте следующий код в класс `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Обработка событий нажатия кнопки  
 Пользователь указывает, что задача ввода данных завершена, нажав кнопку « **ОК** » или « **Отмена** ». Обе кнопки используют один обработчик <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий `ButtonClicked`. Обе кнопки имеют имя, `btnOK` или `btnCancel`, что позволяет обработчику определить, какая кнопка была нажата, проверив значение аргумента `sender`. Обработчик выполняет следующие действия:  
  
- Создает объект `MyControlEventArgs`, содержащий данные из элементов <xref:System.Windows.Controls.TextBox>.  
  
- Если пользователь нажмет кнопку **Отмена** , присваивает свойству `IsOK` объекта `MyControlEventArgs` значение `false`.  
  
- Вызывает событие `OnButtonClick`, чтобы указать узлу, что пользователь завершил работу, и передать собранные данные обратно.  
  
 Добавьте следующий код в класс `MyControl1` после метода `Init`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Создание свойств  
 Оставшаяся часть класса просто предоставляет свойства, которые соответствуют описанным выше глобальным переменным. При изменении свойства метод доступа set изменяет внешний вид элемента управления путем изменения соответствующих свойств элемента и обновления базовых глобальных переменных.  
  
 Добавьте следующий код в класс `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Отправка данных обратно в ведущее приложение  
 Последним компонентом в файле является класс `MyControlEventArgs`, который используется для отправки собранных данных обратно на узел.  
  
 Добавьте следующий код в пространство имен `MyControls`. Реализация является простой и далее не рассматривается.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Постройте решение. В результате сборки будет создана библиотека DLL с именем MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Реализация ведущего приложения Windows Forms  
 Ведущее приложение Windows Forms использует объект <xref:System.Windows.Forms.Integration.ElementHost> для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления. Приложение обрабатывает событие `OnButtonClick` для получения данных из составного элемента управления. Приложение также содержит набор переключателей, которые можно использовать для изменения внешнего вида элемента управления. На рисунке ниже показано приложение.  

На следующем рисунке показан составной элемент управления WPF, размещенный в Windows Forms приложении ".  

 ![Сктиншот, показывающий форму Windows, в которой размещен элемент управления Avalon.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1. Запустите Visual Studio и откройте диалоговое окно **Создание проекта** .  
  
2. В визуальном C# элементе и категории Windows выберите шаблон **приложения Windows Forms** .  
  
3. Присвойте проекту имя `WFHost`.  
  
4. В качестве расположения укажите ту же папку верхнего уровня, в которой содержится проект MyControls.  
  
5. Нажмите кнопку **ОК**, чтобы создать проект.  
  
 Также необходимо добавить ссылки на библиотеку DLL, содержащую `MyControl1` и другие сборки.  
  
1. Щелкните правой кнопкой мыши имя проекта в обозреватель решений и выберите команду **Добавить ссылку**.  
  
2. Перейдите на вкладку **Обзор** и перейдите в папку, содержащую файл MyControls. dll. В данном пошаговом руководстве это папка MyControls\bin\Debug.  
  
3. Выберите файл MyControls. dll и нажмите кнопку **ОК**.  
  
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
  
3. В правом верхнем углу формы добавьте <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> элемент управления для хранения составного элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
4. Добавьте в форму следующие элементы управления <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>.  
  
    |Название|Text|  
    |----------|----------|  
    |groupBox1|Цвет фона|  
    |groupBox2|Цвет переднего плана|  
    |groupBox3|Размер шрифта|  
    |groupBox4|Семейство шрифтов|  
    |groupBox5|Стиль шрифта|  
    |groupBox6|Насыщенность шрифта|  
    |groupBox7|Данные из элемента управления|  
  
5. Добавьте в элементы управления <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> следующие элементы управления <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType>.  
  
    |GroupBox|Название|Text|  
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
  
6. Добавьте в последнюю <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>следующие элементы управления <xref:System.Windows.Forms.Label?displayProperty=nameWithType>. Эти элементы управления отображают данные, возвращаемые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составным элементом управления.  
  
    |GroupBox|Название|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Имя.|  
    |groupBox7|lblAddress|Почтовый адрес:|  
    |groupBox7|lblCity|Город:|  
    |groupBox7|lblState|Состояние:|  
    |groupBox7|lblZip|Почтовый индекс:|  
  
### <a name="initializing-the-form"></a>Инициализация формы  
 Код размещения обычно реализуется в обработчике событий <xref:System.Windows.Forms.Form.Load> формы. В следующем коде показан обработчик событий <xref:System.Windows.Forms.Form.Load>, обработчик для <xref:System.Windows.FrameworkElement.Loaded>ного события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления и объявления для нескольких глобальных переменных, которые используются позже.  
  
 В конструктор Windows Forms дважды щелкните форму, чтобы создать <xref:System.Windows.Forms.Form.Load> обработчик событий. В верхней части Form1.cs добавьте следующие операторы `using`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Замените содержимое существующего класса `Form1` следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Метод `Form1_Load` в приведенном выше коде демонстрирует общую процедуру размещения элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
1. Создайте новый объект <xref:System.Windows.Forms.Integration.ElementHost>.  
  
2. Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления значение <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>.  
  
3. Добавьте элемент управления <xref:System.Windows.Forms.Integration.ElementHost> в коллекцию <xref:System.Windows.Forms.Control.Controls%2A> элемента управления <xref:System.Windows.Forms.Panel>.  
  
4. Создайте экземпляр элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
5. Разместите составной элемент управления в форме, назначив элемент управления свойству <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
 Остальные две строки в методе `Form1_Load` присоединяют обработчики к двум событиям элемента управления:  
  
- `OnButtonClick` — это пользовательское событие, запускаемое составным элементом управления, когда пользователь нажимает кнопку **ОК** или **Отмена** . Обработайте событие для получения ответа пользователя и сбора всех введенных им данных.  
  
- <xref:System.Windows.FrameworkElement.Loaded> является стандартным событием, которое вызывается элементом управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], когда он полностью загружен. Это событие используется здесь потому, что для примера необходима инициализация нескольких глобальных переменных свойствами элемента управления. На момент события <xref:System.Windows.Forms.Form.Load> формы элемент управления не полностью загружен, и для этих значений по-прежнему устанавливается значение `null`. Прежде чем можно будет получить доступ к этим свойствам, необходимо дождаться возникновения события <xref:System.Windows.FrameworkElement.Loaded> элемента управления.  
  
 Обработчик событий <xref:System.Windows.FrameworkElement.Loaded> показан в предыдущем коде. Обработчик `OnButtonClick` рассматривается в следующем разделе.  
  
### <a name="handling-onbuttonclick"></a>Обработка события OnButtonClick  
 Событие `OnButtonClick` возникает, когда пользователь нажимает кнопку **ОК** или **Отмена** .  
  
 Обработчик событий проверяет поле `IsOK` аргумента события, чтобы определить, какая кнопка была нажата. `lbl`переменные *данных* соответствуют элементам управления <xref:System.Windows.Forms.Label>, которые были рассмотрены ранее. Если пользователь нажмет кнопку **ОК** , данные из элементов управления <xref:System.Windows.Controls.TextBox> элемента управления назначаются соответствующему элементу управления <xref:System.Windows.Forms.Label>. Если пользователь нажимает кнопку **Отмена**, <xref:System.Windows.Forms.Label.Text%2A> значения задаются в виде строк по умолчанию.  
  
 Добавьте следующий код обработчика событий нажатием кнопки в класс `Form1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Выполните сборку и запуск приложения. Добавьте некоторый текст в составной элемент управления WPF и нажмите кнопку **ОК**. Этот текст появится в метках. На данном этапе код для обработки переключателей еще не добавлен.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Изменение внешнего вида элемента управления  
 Элементы управления <xref:System.Windows.Forms.RadioButton> в форме позволят пользователю изменять цвет переднего плана и цвета фона [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления, а также несколько свойств шрифта. Цвет фона предоставляется объектом <xref:System.Windows.Forms.Integration.ElementHost>. Остальные свойства предоставляются как настраиваемые свойства элемента управления.  
  
 Дважды щелкните каждый <xref:System.Windows.Forms.RadioButton> элемент управления в форме, чтобы создать <xref:System.Windows.Forms.RadioButton.CheckedChanged> обработчики событий. Замените обработчики событий <xref:System.Windows.Forms.RadioButton.CheckedChanged> следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Выполните сборку и запуск приложения. Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в составном элементе управления WPF.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
