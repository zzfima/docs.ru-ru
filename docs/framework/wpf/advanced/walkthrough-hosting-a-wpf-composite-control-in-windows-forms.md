---
title: Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: a062095885e6c1fc8816a78847968b1c250eabf8
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991448"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms
Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений. Однако при наличии значительных инвестиций в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] код может оказаться более эффективным расширение существующего [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , а не переписывание его с нуля. Распространенный сценарий заключается в том, что необходимо внедрить один или несколько элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , реализованных в приложении Windows Forms. Дополнительные сведения о настройке элементов управления WPF см. в разделе [Настройка элемента управления](../controls/control-customization.md).  
  
 В этом пошаговом руководстве описывается приложение, в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] котором размещен составной элемент управления для выполнения записи данных в Windows Forms приложении. Составной элемент управления упакован в библиотеку DLL. Эта общая процедура может быть расширена для более сложных приложений и элементов управления. Это пошаговое руководство призвано стать практически идентичным по внешнему виду и функциональности для [пошагового руководства. Размещение Windows Forms составного элемента управления в](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)WPF. Основным отличием является то, что сценарий размещения выполняется в обратном порядке.  
  
 Пошаговое руководство состоит из двух разделов. В первом разделе кратко описывается реализация [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления. Во втором разделе подробно рассматривается размещение составного элемента управления в Windows Forms приложении, получение событий из элемента управления и доступ к некоторым свойствам элемента управления.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
- Реализация составного элемента управления WPF  
  
- Реализация ведущего приложения Windows Forms  
  
 Полный листинг кода задач, показанных в этом пошаговом руководстве, см. [в разделе размещение составного элемента управления WPF в Windows Forms примере](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl).  
  
## <a name="prerequisites"></a>Предварительные требования  

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.  
  
## <a name="implementing-the-wpf-composite-control"></a>Реализация составного элемента управления WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Составной элемент управления, используемый в этом примере, представляет собой простую форму ввода данных, которая принимает имя и адрес пользователя. Когда пользователь нажимает одну из двух кнопок, чтобы указать, что задача завершена, элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение. На приведенном ниже рисунке показан отображаемый элемент управления. 

 На следующем рисунке показан составной элемент управления WPF: 

 ![Снимок экрана, на котором показан простой элемент управления WPF.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1. Запустите [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]и откройте диалоговое окно **Создание проекта** .  
  
2. В области C# визуальные элементы и Категория Windows выберите шаблон **Библиотека пользовательского элемента управления WPF** .  
  
3. Присвойте проекту имя `MyControls`.  
  
4. В качестве расположения укажите папку верхнего уровня с удобным именем, например `WindowsFormsHostingWpfControl`. Позже ведущее приложение будет помещено в эту папку.  
  
5. Нажмите кнопку **ОК**, чтобы создать проект. Проект по умолчанию содержит один элемент управления `UserControl1`с именем.  
  
6. В Обозреватель решений переименуйте `UserControl1` в `MyControl1`.  
  
 Проект должен иметь ссылки на перечисленные ниже системные библиотеки DLL. Если какие-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.  
  
- PresentationCore  
  
- PresentationFramework  
  
- Система  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Создание пользовательского интерфейса  
 Для составного элемента управления реализуется с [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]помощью. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Составной элемент [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] управления состоит из <xref:System.Windows.Controls.TextBox> пяти элементов. Каждый <xref:System.Windows.Controls.TextBox> элемент имеет связанный <xref:System.Windows.Controls.TextBlock> элемент, который выступает в качестве метки. В нижней части <xref:System.Windows.Controls.Button> есть два элемента: **ОК** и **Отмена**. При нажатии любой кнопки элемент управления создает пользовательское событие для возвращения сведений в ведущее приложение.  
  
#### <a name="basic-layout"></a>Базовый макет  
 Различные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы содержатся <xref:System.Windows.Controls.Grid> в элементе. Можно использовать <xref:System.Windows.Controls.Grid> для размещения содержимого составного элемента управления во многом так же, как при `Table` использовании элемента в HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]также содержит <xref:System.Windows.Documents.Table> элемент, но <xref:System.Windows.Controls.Grid> он более прост и лучше подходит для простых задач макета.  
  
 В приведенном ниже коде XAML показан базовый макет. Этот XAML определяет общую структуру элемента управления, указывая количество столбцов и строк в <xref:System.Windows.Controls.Grid> элементе.  
  
 В файле MyControl1.xaml замените имеющийся код XAML приведенным ниже кодом.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Добавление в сетку элементов TextBlock и TextBox  
 Чтобы поместить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элемент в сетку, установите атрибуты <xref:System.Windows.Controls.Grid.RowProperty> элемента и <xref:System.Windows.Controls.Grid.ColumnProperty> на соответствующий номер строки и столбца. Следует помнить, что нумерация строк и столбцов ведется от нуля. Элемент может охватывать несколько столбцов, задав его <xref:System.Windows.Controls.Grid.ColumnSpanProperty> атрибут. Дополнительные сведения об <xref:System.Windows.Controls.Grid> элементах см. [в разделе Создание элемента Grid](../controls/how-to-create-a-grid-element.md).  
  
 В следующем коде XAML показаны элементы составного <xref:System.Windows.Controls.TextBox> элемента <xref:System.Windows.Controls.TextBlock> управления и с <xref:System.Windows.Controls.Grid.RowProperty> их <xref:System.Windows.Controls.Grid.ColumnProperty> атрибутами и, которые устанавливаются для правильного размещения элементов в сетке.  
  
 В файле MyControl1. XAML добавьте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Создание стилей элементов пользовательского интерфейса  
 Многие элементы в форме для ввода данных имеют одинаковый внешний вид. Это означает, что они имеют одинаковые значения нескольких свойств. Вместо того чтобы задавать атрибуты каждого элемента отдельно, предыдущий XAML использует <xref:System.Windows.Style> элементы для определения стандартных настроек свойств для классов элементов. Такой подход упрощает элемент управления и позволяет изменять внешний вид нескольких элементов посредством одного атрибута стиля.  
  
 Элементы содержатся в свойстве <xref:System.Windows.Controls.Grid> <xref:System.Windows.FrameworkElement.Resources%2A> элемента, поэтому они могут использоваться всеми элементами в элементе управления. <xref:System.Windows.Style> Если стиль называется, он применяется к элементу путем добавления <xref:System.Windows.Style> набора элементов к имени стиля. Неименованные стили становятся стилями по умолчанию для элемента. Дополнительные сведения о [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] стилях см. в разделе [Стилизация и создание шаблонов](../controls/styling-and-templating.md).  
  
 В следующем коде XAML показаны <xref:System.Windows.Style> элементы для составного элемента управления. Чтобы увидеть, как стили применяются к элементам, см. предыдущий код XAML. Например, последний <xref:System.Windows.Controls.TextBlock> элемент `inlineText` имеет стиль, а последний <xref:System.Windows.Controls.TextBox> элемент использует стиль по умолчанию.  
  
 В файле MyControl1. XAML добавьте следующий код XAML сразу после <xref:System.Windows.Controls.Grid> начального элемента.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Добавление кнопок OK и "Отмена"  
 Последними элементами в составном элементе управления являются элементы **OK** и **Cancel** <xref:System.Windows.Controls.Button> , которые занимают первые два столбца последней строки. <xref:System.Windows.Controls.Grid> Эти элементы используют общий обработчик событий, `ButtonClicked`и стиль по умолчанию <xref:System.Windows.Controls.Button> , определенный в предыдущем XAML.  
  
 В файле MyControl1. XAML добавьте следующий код XAML после последнего <xref:System.Windows.Controls.TextBox> элемента. Теперь [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] часть составного элемента управления завершена.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Реализация файла кода программной части  
 Файл кода программной части, MyControl1.xaml.cs, реализует три критических задачи:
  
1. обрабатывает событие, когда пользователь нажимает одну из кнопок;  
  
2. Извлекает данные из <xref:System.Windows.Controls.TextBox> элементов и упаковывает их в объект аргумента пользовательского события.  
  
3. Вызывает пользовательское `OnButtonClick` событие, которое уведомляет узел о завершении работы пользователя и передает данные на узел.  
  
 Элемент управления также предоставляет ряд свойств цвета и шрифтов, которые позволяют изменять внешний вид. В <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Controls.Panel.Background%2A> отличие от класса, который используется для размещения элемента управления Windows Forms, класс предоставляет только свойство элемента управления. <xref:System.Windows.Forms.Integration.ElementHost> Чтобы сохранить сходство между этим примером кода и примером, описанным в [разделе Пошаговое руководство: Разместив Windows Forms составного элемента управления](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)в WPF, элемент управления предоставляет оставшиеся свойства напрямую.  
  
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
  
 Первый класс `MyControl1`,, является разделяемым классом, содержащим код, реализующий функциональные возможности, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] определенные в файле MyControl1. XAML. При синтаксическом анализе [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файле MyControl1. XAML преобразуется в тот же разделяемый класс, а два разделяемых класса объединяются для формирования скомпилированного элемента управления. По этой причине имя класса в файле кода программной части должно совпадать с именем класса, назначенным в файле MyControl1.xaml, и наследоваться от корневого элемента управления. Второй класс, `MyControlEventArgs`, является классом аргументов события, который используется для отправки данных на узел.  
  
 Откройте файл MyControl1.xaml.cs. Измените существующее объявление класса таким образом, чтобы оно получило следующее имя и наследовало от <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Инициализация элемента управления  
 Приведенный ниже код реализует несколько основных задач:  
  
- Объявляет закрытое событие `OnButtonClick`, и связанный с ним `MyControlEventHandler`делегат.  
  
- создает несколько частных глобальных переменных, хранящих данные пользователя. Эти данные предоставляются через соответствующие свойства;  
  
- Реализует обработчик `Init`для <xref:System.Windows.FrameworkElement.Loaded> события элемента управления. Этот обработчик инициализирует глобальные переменные путем присвоения им значений, определенных в файле MyControl1.xaml. Для этого используется объект <xref:System.Windows.FrameworkElement.Name%2A> , назначенный стандартному <xref:System.Windows.Controls.TextBlock> элементу, `nameLabel`для доступа к параметрам свойств этого элемента.  
  
 Удалите существующий конструктор и добавьте следующий код в `MyControl1` класс.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Обработка событий нажатия кнопки  
 Пользователь указывает, что задача ввода данных завершена, нажав кнопку « **ОК** » или « **Отмена** ». Обе кнопки используют один и <xref:System.Windows.Controls.Primitives.ButtonBase.Click> тот же `ButtonClicked`обработчик событий. У обеих кнопок есть имя, `btnOK` или `btnCancel`, которое позволяет обработчику определить, какая кнопка была нажата, изучив значение `sender` аргумента. Обработчик выполняет следующие действия:  
  
- Создает объект, содержащий данные <xref:System.Windows.Controls.TextBox> из элементов. `MyControlEventArgs`  
  
- Если пользователь нажмет кнопку **Отмена** `MyControlEventArgs` , `IsOK` свойству `false`объекта присваивается значение.  
  
- `OnButtonClick` Вызывает событие, чтобы указать узлу, что пользователь завершил работу, и передать собранные данные обратно.  
  
 Добавьте следующий код в `MyControl1` класс `Init` после метода.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Создание свойств  
 Оставшаяся часть класса просто предоставляет свойства, которые соответствуют описанным выше глобальным переменным. При изменении свойства метод доступа set изменяет внешний вид элемента управления путем изменения соответствующих свойств элемента и обновления базовых глобальных переменных.  
  
 Добавьте в `MyControl1` класс следующий код.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Отправка данных обратно в ведущее приложение  
 Последним компонентом в файле является `MyControlEventArgs` класс, который используется для отправки собранных данных обратно на узел.  
  
 Добавьте следующий код в `MyControls` пространство имен. Реализация является простой и далее не рассматривается.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Постройте решение. В результате сборки будет создана библиотека DLL с именем MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Реализация ведущего приложения Windows Forms  
 Ведущее приложение Windows Forms использует <xref:System.Windows.Forms.Integration.ElementHost> объект для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещения составного элемента управления. Приложение обрабатывает `OnButtonClick` событие для получения данных из составного элемента управления. Приложение также содержит набор переключателей, которые можно использовать для изменения внешнего вида элемента управления. На рисунке ниже показано приложение.  

На следующем рисунке показан составной элемент управления WPF, размещенный в Windows Forms приложении ".  

 ![Сктиншот, показывающий форму Windows, в которой размещен элемент управления Avalon.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Создание проекта  
 Для запуска проекта выполните указанные ниже действия.  
  
1. Запустите [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]и откройте диалоговое окно **Создание проекта** .  
  
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
  
3. В правом верхнем углу формы добавьте <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> элемент управления для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] хранения составного элемента управления.  
  
4. Добавьте в форму <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> следующие элементы управления.  
  
    |name|Текст|  
    |----------|----------|  
    |groupBox1|Цвет фона|  
    |groupBox2|Цвет переднего плана|  
    |groupBox3|Размер шрифта|  
    |groupBox4|Семейство шрифтов|  
    |groupBox5|Стиль шрифта|  
    |groupBox6|Насыщенность шрифта|  
    |groupBox7|Данные из элемента управления|  
  
5. Добавьте в <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> элементы <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> управления следующие элементы управления.  
  
    |GroupBox|name|Текст|  
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
    |groupBox5|radioStyleOriginal|Обычный|  
    |groupBox5|radioStyleItalic|Italic|  
    |groupBox6|radioWeightOriginal|До преобразования|  
    |groupBox6|radioWeightBold|Полужирный|  
  
6. Добавьте следующие <xref:System.Windows.Forms.Label?displayProperty=nameWithType> элементы управления в последнюю <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>. Эти элементы управления отображают данные, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возвращаемые составным элементом управления.  
  
    |GroupBox|name|Текст|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Имя.|  
    |groupBox7|lblAddress|Почтовый адрес:|  
    |groupBox7|lblCity|Город:|  
    |groupBox7|lblState|Состояние:|  
    |groupBox7|lblZip|Почтовый индекс:|  
  
### <a name="initializing-the-form"></a>Инициализация формы  
 Код размещения обычно реализуется в обработчике <xref:System.Windows.Forms.Form.Load> событий формы. В следующем коде показан <xref:System.Windows.Forms.Form.Load> обработчик событий, обработчик [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для <xref:System.Windows.FrameworkElement.Loaded> события составного элемента управления и объявления для нескольких глобальных переменных, которые используются позже.  
  
 В конструктор Windows Forms дважды щелкните форму, чтобы создать <xref:System.Windows.Forms.Form.Load> обработчик событий. В верхней части Form1.cs добавьте следующие `using` инструкции.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Замените содержимое существующего `Form1` класса следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Метод в предыдущем коде показывает общую процедуру [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] размещения элемента управления: `Form1_Load`  
  
1. Создайте новый <xref:System.Windows.Forms.Integration.ElementHost> объект.  
  
2. <xref:System.Windows.Forms.Control.Dock%2A> Присвойте<xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>свойству элемента управления значение.  
  
3. Добавьте элемент управления <xref:System.Windows.Forms.Panel> в <xref:System.Windows.Forms.Control.Controls%2A> коллекцию элемента управления. <xref:System.Windows.Forms.Integration.ElementHost>  
  
4. Создайте экземпляр [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемента управления.  
  
5. Разместите составной элемент управления в форме, назначив элемент управления <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> свойству элемента управления.  
  
 Остальные две строки в `Form1_Load` методе присоединяют обработчики к двум событиям элемента управления:  
  
- `OnButtonClick`пользовательское событие, запускаемое составным элементом управления, когда пользователь нажимает кнопку **ОК** или **Отмена** . Обработайте событие для получения ответа пользователя и сбора всех введенных им данных.  
  
- <xref:System.Windows.FrameworkElement.Loaded>стандартное событие, создаваемое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементом управления при полной загрузке. Это событие используется здесь потому, что для примера необходима инициализация нескольких глобальных переменных свойствами элемента управления. На момент <xref:System.Windows.Forms.Form.Load> события формы элемент управления не полностью загружен, и для `null`этих значений по-прежнему устанавливается значение. Прежде чем можно будет получить доступ к этим <xref:System.Windows.FrameworkElement.Loaded> свойствам, необходимо дождаться события элемента управления.  
  
 Обработчик <xref:System.Windows.FrameworkElement.Loaded> событий показан в приведенном выше коде. `OnButtonClick` Обработчик обсуждается в следующем разделе.  
  
### <a name="handling-onbuttonclick"></a>Обработка события OnButtonClick  
 Это `OnButtonClick` событие возникает при нажатии пользователем кнопки **ОК** или **Отмена** .  
  
 Обработчик событий проверяет `IsOK` поле аргумента события, чтобы определить, какая кнопка была нажата. Переменные данных соответствуют элементамуправления,которыебылирассмотрены<xref:System.Windows.Forms.Label>ранее. `lbl` Если пользователь нажимает кнопку « **ОК** », данные из <xref:System.Windows.Controls.TextBox> элементов управления элемента управления назначаются соответствующему <xref:System.Windows.Forms.Label> элементу управления. Если пользователь нажимает кнопку **Отмена**, <xref:System.Windows.Forms.Label.Text%2A> значения задаются в виде строк по умолчанию.  
  
 Добавьте следующий код обработчика событий нажатием кнопки в `Form1` класс.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Выполните сборку и запуск приложения. Добавьте некоторый текст в составной элемент управления WPF и нажмите кнопку **ОК**. Текст отображается в метках. На данном этапе код для обработки переключателей еще не добавлен.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Изменение внешнего вида элемента управления  
 Элементы управления в форме позволят пользователю [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] изменять цвет переднего плана и фона для составного элемента управления, а также несколько свойств шрифта. <xref:System.Windows.Forms.RadioButton> Цвет фона предоставляется <xref:System.Windows.Forms.Integration.ElementHost> объектом. Остальные свойства предоставляются как настраиваемые свойства элемента управления.  
  
 Дважды щелкните каждый <xref:System.Windows.Forms.RadioButton> элемент управления в форме, чтобы создать <xref:System.Windows.Forms.RadioButton.CheckedChanged> обработчики событий. Замените обработчики <xref:System.Windows.Forms.RadioButton.CheckedChanged> событий следующим кодом.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Выполните сборку и запуск приложения. Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в составном элементе управления WPF.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Пошаговое руководство: Размещение составного элемента управления Windows Forms в WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Пошаговое руководство: Размещение трехмерного составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
