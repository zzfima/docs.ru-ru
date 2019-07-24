---
title: Общие сведения о шаблонах данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: 556ce7b42f13d7c5ba7fba36b09277cda9bcae5d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400657"
---
# <a name="data-templating-overview"></a>Общие сведения о шаблонах данных
Модель шаблонов данных WPF предоставляет большую гибкость при определении представления данных. Элементы управления WPF имеют встроенные функции для поддержки настройки представления данных. В этом разделе сначала показано, как определить <xref:System.Windows.DataTemplate> , а затем появились другие возможности создания шаблонов данных, такие как выбор шаблонов на основе пользовательской логики и поддержка отображения иерархических данных.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе рассматриваются функции шаблонов данных. Здесь отсутствуют общие сведения о понятиях привязки данных. Сведения о базовых концепциях привязки данных содержатся в разделе [Обзор привязки данных](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate>является представлением данных и является одной из многих функций, предоставляемых моделью стилизации и шаблонов WPF. Общие сведения о модели стилизации и шаблонов WPF, например о том, как использовать <xref:System.Windows.Style> для задания свойств элементов управления, см. в разделе Стилизация [и шаблоны](../controls/styling-and-templating.md) .  
  
 Кроме того, важно понимать `Resources`, что по сути позволяет использовать объекты, такие как <xref:System.Windows.Style> и, <xref:System.Windows.DataTemplate> для многократного использования. Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Основные сведения о шаблонах данных  
  
 Чтобы продемонстрировать, <xref:System.Windows.DataTemplate> почему это важно, давайте рассмотрим пример привязки данных. В этом примере есть <xref:System.Windows.Controls.ListBox> привязка, привязанная к `Task` списку объектов. Каждому `Task` объекту соответствует `TaskName` (строка), `Description` (строка), `Priority` (int) и свойство типа `TaskType`, которое является `Enum` со значениями `Home` и `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Без шаблона данных DataTemplate  
 В настоящее время наш <xref:System.Windows.Controls.ListBox> код выглядит следующим образом: <xref:System.Windows.DataTemplate>  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Что происходит без каких-либо специальных инструкций, <xref:System.Windows.Controls.ListBox> по умолчанию вызывается `ToString` при попытке отобразить объекты в коллекции. Таким образом, если `Task` объект `ToString` переопределяет метод, то <xref:System.Windows.Controls.ListBox> отображает строковое представление каждого исходного объекта в базовой коллекции.  
  
 Например, если класс `Task` переопределяет метод `ToString` таким образом, что `name` — поле для `TaskName` свойства:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Затем он <xref:System.Windows.Controls.ListBox> выглядит следующим образом:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Тем не менее это характеризуется ограниченностью и негибкостью. Кроме того, если выполняется привязка к данным[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], невозможно переопределить `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Определение простого шаблона DataTemplate  
 Решение заключается в определении <xref:System.Windows.DataTemplate>. Одним из способов сделать это является присвоение <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойству значения. <xref:System.Windows.Controls.ListBox> <xref:System.Windows.DataTemplate> То, что вы указываете в <xref:System.Windows.DataTemplate> , станет визуальной структурой объекта данных. Следующий пример <xref:System.Windows.DataTemplate> довольно прост. Мы предоставляем инструкции, которые каждый элемент отображается как три <xref:System.Windows.Controls.TextBlock> элемента <xref:System.Windows.Controls.StackPanel>в. Каждый <xref:System.Windows.Controls.TextBlock> элемент привязан к свойству `Task` класса.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Базовые данные для примеров в этом разделе представляют собой коллекцию объектов CLR. Если выполнить привязку к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], основные понятия схожи, но есть незначительные синтаксические различия. `Path=TaskName`Например, вместо параметра необходимо `@TaskName` задать значение <xref:System.Windows.Data.Binding.XPath%2A> (если `TaskName` является атрибутом вашего [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] узла).  
  
 Теперь наш <xref:System.Windows.Controls.ListBox> вид выглядит следующим образом:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Создание шаблона DataTemplate как ресурса  
 В приведенном выше примере мы определили <xref:System.Windows.DataTemplate> встроенное. Обычно его определяют в разделе ресурсов, чтобы его можно было повторно использовать, как в следующем примере:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Теперь вы можете использовать `myTaskTemplate` в качестве ресурса, как показано в следующем примере:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Так `myTaskTemplate` как является ресурсом, теперь его можно использовать в других элементах управления, имеющих свойство, <xref:System.Windows.DataTemplate> принимающее тип. Как показано выше, для <xref:System.Windows.Controls.ItemsControl> объектов, таких <xref:System.Windows.Controls.ListBox>как, <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> это свойство. Для <xref:System.Windows.Controls.ContentControl> объектов<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> это свойство.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Свойство DataType  
 Класс имеет свойство, которое очень похоже <xref:System.Windows.Style> на <xref:System.Windows.Style.TargetType%2A> свойство класса. <xref:System.Windows.DataTemplate.DataType%2A> <xref:System.Windows.DataTemplate> Таким образом, вместо указания `x:Key` <xref:System.Windows.DataTemplate> для для в приведенном выше примере можно выполнить следующие действия.  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Он <xref:System.Windows.DataTemplate> применяется автоматически ко всем `Task` объектам. Обратите внимание, что в этом случае `x:Key` устанавливается неявно. Таким образом, если вы назначаете `x:Key` это <xref:System.Windows.DataTemplate> значение, вы <xref:System.Windows.DataTemplate> переопределяете неявное `x:Key` и не будет применяться автоматически.  
  
 При привязке <xref:System.Windows.Controls.ContentControl> к `Task` коллекции объектов <xref:System.Windows.Controls.ContentControl> объект не использует приведенный выше <xref:System.Windows.DataTemplate> объект автоматически. Это обусловлено тем, что для <xref:System.Windows.Controls.ContentControl> привязки к требуется больше сведений, чтобы определить, нужно ли выполнять привязку к целой коллекции или к отдельным объектам. <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Controls.ContentControl> `/`Если вы отслеживаете выбор <xref:System.Windows.Controls.ItemsControl> типа, можно присвоить свойству привязки значение "", чтобы указать, что вы заинтересованы в текущем элементе. <xref:System.Windows.Controls.ContentControl> Для примера см. [Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). В противном случае необходимо <xref:System.Windows.DataTemplate> явно <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> указать значение свойства.  
  
 Свойство особенно полезно при <xref:System.Windows.Data.CompositeCollection> наличии различных типов объектов данных. <xref:System.Windows.DataTemplate.DataType%2A> Пример см. в разделе [Реализация CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Добавление дополнительных данных в DataTemplate  
 В настоящее время данные содержат необходимую информацию, но определенно это можно улучшить. Давайте улучшаем презентацию, добавляя <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Grid>, и некоторые <xref:System.Windows.Controls.TextBlock> элементы, описывающие отображаемые данные.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 На следующем снимке экрана <xref:System.Windows.Controls.ListBox> показано, что <xref:System.Windows.DataTemplate>изменилось:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Мы можем задать <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> для <xref:System.Windows.HorizontalAlignment.Stretch> значение ON <xref:System.Windows.Controls.ListBox> , чтобы убедиться, что ширина элементов занимает все пространство:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Если свойство имеет <xref:System.Windows.HorizontalAlignment.Stretch>значение, теперь он <xref:System.Windows.Controls.ListBox> выглядит следующим образом: <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Использование триггеров данных для применения значений свойств  
 В настоящей презентации не говорится о том, является ли `Task` домашней задачей или офисной. Помните, что объект `Task` имеет свойство `TaskType` типа `TaskType`, который является перечислением со значениями `Home` и `Work`.  
  
 В следующем <xref:System.Windows.DataTrigger> примере параметр <xref:System.Windows.Controls.Border.BorderBrush%2A> задает для `border` `Yellow` элементас`TaskType.Home`именем значение, если свойствоимеетзначение.`TaskType`  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Наше приложение теперь выглядит следующим образом. Домашние задачи отображаются с желтой границей, а офисные — с синей границей:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 В этом примере <xref:System.Windows.DataTrigger> <xref:System.Windows.Setter> компонент использует для задания значения свойства. Классы триггеров также имеют <xref:System.Windows.TriggerBase.EnterActions%2A> свойства и <xref:System.Windows.TriggerBase.ExitActions%2A> , позволяющие запускать набор действий, таких как анимация. Кроме того, существует также <xref:System.Windows.MultiDataTrigger> класс, позволяющий применять изменения на основе нескольких значений свойств, привязанных к данным.  
  
 Другой способ добиться того же результата — привязать <xref:System.Windows.Controls.Border.BorderBrush%2A> свойство `TaskType` к свойству и использовать преобразователь значений для возврата цвета на основе `TaskType` значения. Создание вышеупомянутого эффекта с помощью преобразователя является немного более эффективным с точки зрения производительности. Кроме того, создание собственных преобразователей обеспечивает большую гибкость, так как вы предоставляете свою собственную логику. В конечном счете выбор техники зависит от сценария и предпочтений. Дополнительные сведения о создании преобразователя см. в разделе <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Что входит в DataTemplate?  

В предыдущем примере мы поместили триггер <xref:System.Windows.DataTemplate> в с <xref:System.Windows.DataTemplate>помощью.<xref:System.Windows.DataTemplate.Triggers%2A> . Триггер задает значение свойства элемента <xref:System.Windows.Controls.Border> (элемента <xref:System.Windows.DataTemplate>), который находится в. <xref:System.Windows.Setter> Однако если свойства `Setters` , с которыми связаны вопросы, не являются свойствами элементов, находящихся в текущем <xref:System.Windows.DataTemplate>объекте, то может оказаться более подходящим <xref:System.Windows.Style> задание свойств с помощью <xref:System.Windows.Controls.ListBoxItem> класса, который предназначен для этого (если элемент управления, к <xref:System.Windows.Controls.ListBox>которому выполняется привязка, —). Например, если нужно <xref:System.Windows.Trigger> <xref:System.Windows.UIElement.Opacity%2A> анимировать значение элемента при наведении указателя мыши на элемент, <xref:System.Windows.Controls.ListBoxItem> можно определить триггеры в стиле. Пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 В общем случае помните, что <xref:System.Windows.DataTemplate> применяется к каждому из созданных <xref:System.Windows.Controls.ListBoxItem> (Дополнительные сведения о том, как и где она применяется, см. на <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> странице). Для <xref:System.Windows.DataTemplate> вас важна только презентация и внешний вид объектов данных. В большинстве случаев все остальные аспекты презентации, например сведения о том, как выглядит элемент, когда он выбран, или о том <xref:System.Windows.Controls.ListBox> , как размещает элементы, не принадлежат в определении. <xref:System.Windows.DataTemplate> Пример см. в разделе [Стилизация и использование шаблонов для ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Выбор DataTemplate на основе свойств объекта данных  
 В разделе [Свойство DataType](#Styling_DataType) мы говорили о том, что можно определить различные шаблоны данных для различных объектов данных. Это особенно полезно при наличии <xref:System.Windows.Data.CompositeCollection> различных типов или коллекций с элементами различных типов. В разделе [Использование триггеров данных для применения значений свойств](#DataTrigger_to_Apply_Property_Values) мы показали, что при наличии коллекции одного <xref:System.Windows.DataTemplate> и того же типа объектов Data можно создать, а затем использовать триггеры для применения изменений на основе значений свойств каждого объекта данных. Тем не менее, хотя триггеры позволяют применить значения свойств или запустить анимацию, они не предоставляют гибкость, достаточную для реконструкции структуры объектов данных. Некоторые сценарии могут потребовать создания различных <xref:System.Windows.DataTemplate> объектов данных одного типа, но имеют разные свойства.  
  
 Например, если объект `Task` имеет значение `Priority` свойства `1`, вы можете задать совершенно другой вид для него, чтобы сделать его сигналом оповещения. В этом случае для просмотра объектов с <xref:System.Windows.DataTemplate> высоким приоритетом `Task` создается объект. Добавим следующий <xref:System.Windows.DataTemplate> элемент в раздел Resources:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Обратите внимание, что <xref:System.Windows.DataTemplate>в этом примере используется.<xref:System.Windows.FrameworkTemplate.Resources%2A> . Ресурсы, определенные в этом разделе, совместно используются элементами <xref:System.Windows.DataTemplate>в.  
  
 Чтобы указать логику <xref:System.Windows.DataTemplate> , используемую в зависимости `Priority` от значения объекта данных, создайте <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> подкласс класса <xref:System.Windows.Controls.DataTemplateSelector> и переопределите метод. В следующем примере <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> метод предоставляет логику для возврата соответствующего шаблона на основе значения `Priority` свойства. Возвращаемый шаблон находится в ресурсах элемента запечатывание <xref:System.Windows.Window> .  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Затем можно объявить `TaskListDataTemplateSelector` как ресурс:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Чтобы использовать ресурс селектора шаблона, назначьте его <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> свойству <xref:System.Windows.Controls.ListBox>объекта. <xref:System.Windows.Controls.ListBox> Вызывает<xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> метод для`TaskListDataTemplateSelector` каждого элемента в базовой коллекции. Вызов передает объект данных в качестве параметра элемента. Объект <xref:System.Windows.DataTemplate> , возвращаемый методом, затем применяется к этому объекту данных.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 С помощью селектора <xref:System.Windows.Controls.ListBox> шаблона теперь отображается следующее:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Это заключительный шаг нашего обсуждения данного примера. Полный пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Стилизация и использование шаблонов для ItemsControl  
 Несмотря на то, что не единственный тип элемента управления, <xref:System.Windows.DataTemplate> с помощью которого можно использовать, это очень <xref:System.Windows.Controls.ItemsControl> распространенный сценарий для привязки к коллекции. <xref:System.Windows.Controls.ItemsControl> В разделе [что входит в DataTemplate](#what_belongs_in_datatemplate) мы обсуждали, что определение <xref:System.Windows.DataTemplate> должно быть связано только с представлением данных. Чтобы узнать, когда не подходит использовать, <xref:System.Windows.DataTemplate> важно понимать различные свойства стиля и шаблона, предоставляемые. <xref:System.Windows.Controls.ItemsControl> Следующий пример предназначен для демонстрации функции каждого из этих свойств. В этом примере Привязка выполняется к той же `Tasks` коллекции, что и в предыдущем примере. <xref:System.Windows.Controls.ItemsControl> Для демонстрационных целей все стили и шаблоны в этом примере объявлены встроенными.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Ниже приведен снимок экрана примера при его просмотре:  
  
 ![Снимок экрана примера ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Обратите внимание, что вместо <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>использования можно <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>использовать. Пример см. в предыдущем разделе. Аналогично, вместо использования <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>можно <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>использовать.  
  
 Два других свойства, относящиеся к <xref:System.Windows.Controls.ItemsControl> стилю, не показаны здесь, — <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> и. <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Поддержка иерархических данных  
 Пока мы только рассматривали как привязывать и отображать одну коллекцию. Иногда встречается коллекция, содержащая другие коллекции. Класс предназначен для использования с <xref:System.Windows.Controls.HeaderedItemsControl> типами для вывода таких данных. <xref:System.Windows.HierarchicalDataTemplate> В следующем примере `ListLeagueList` является списком объектов `League`. Каждый объект `League` содержит `Name` и коллекцию объектов `Division`. Каждый `Division` содержит `Name` и коллекцию объектов `Team`, и каждый объект `Team` содержит `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 В примере показано, что с помощью <xref:System.Windows.HierarchicalDataTemplate>можно легко отобразить список данных, содержащих другие списки. Ниже приведен снимок экрана примера.  
  
 ![Снимок экрана образца HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>См. также

- [Привязка данных](../advanced/optimizing-performance-data-binding.md)
- [Поиск элементов, созданных с использованием шаблона DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Стилизация и использование шаблонов](../controls/styling-and-templating.md)
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Общие сведения о стилях заголовков столбцов GridView и шаблонах](../controls/gridview-column-header-styles-and-templates-overview.md)
