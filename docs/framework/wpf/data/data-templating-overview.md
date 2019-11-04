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
ms.openlocfilehash: d088342a08076c69b34f6c3d39dce076cb3890d4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460050"
---
# <a name="data-templating-overview"></a>Общие сведения о шаблонах данных
Модель шаблонов данных WPF предоставляет большую гибкость при определении представления данных. Элементы управления WPF имеют встроенные функции для поддержки настройки представления данных. В этом разделе сначала показано, как определить <xref:System.Windows.DataTemplate> а затем появились другие возможности создания шаблонов данных, такие как выбор шаблонов на основе пользовательской логики и поддержка отображения иерархических данных.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Необходимые компоненты  
 В этом разделе рассматриваются функции шаблонов данных. Здесь отсутствуют общие сведения о понятиях привязки данных. Сведения о базовых концепциях привязки данных содержатся в разделе [Обзор привязки данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> представляет собой представление данных и является одной из многих функций, предоставляемых моделью стилизации и шаблонов WPF. Общие сведения о модели стилизации и шаблонов WPF, например об использовании <xref:System.Windows.Style> для задания свойств элементов управления, см. в разделе [Стилизация и создание шаблонов](../controls/styling-and-templating.md) .  
  
 Кроме того, важно понимать `Resources`, которые, по сути, позволяют использовать такие объекты, как <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate>. Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Основные сведения о шаблонах данных  
  
 Чтобы продемонстрировать, зачем <xref:System.Windows.DataTemplate> важно, давайте рассмотрим пример привязки данных. В этом примере имеется <xref:System.Windows.Controls.ListBox>, привязанный к списку объектов `Task`. Каждому `Task` объекту соответствует `TaskName` (строка), `Description` (строка), `Priority` (int) и свойство типа `TaskType`, которое является `Enum` со значениями `Home` и `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Без шаблона данных DataTemplate  
 Без <xref:System.Windows.DataTemplate>наш <xref:System.Windows.Controls.ListBox> в настоящее время выглядит следующим образом:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Что происходит без каких-либо специальных инструкций, <xref:System.Windows.Controls.ListBox> по умолчанию вызывает `ToString` при попытке отобразить объекты в коллекции. Таким образом, если объект `Task` переопределяет метод `ToString`, <xref:System.Windows.Controls.ListBox> отображает строковое представление каждого исходного объекта в базовой коллекции.  
  
 Например, если класс `Task` переопределяет метод `ToString` таким образом, что `name` — поле для `TaskName` свойства:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Затем <xref:System.Windows.Controls.ListBox> выглядит следующим образом:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Тем не менее это характеризуется ограниченностью и негибкостью. Кроме того, если выполняется привязка к данным[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], невозможно переопределить `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Определение простого шаблона DataTemplate  
 Решение заключается в определении <xref:System.Windows.DataTemplate>. Один из способов сделать это — задать для свойства <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ListBox> значение <xref:System.Windows.DataTemplate>. То, что указывается в <xref:System.Windows.DataTemplate>, превращается в визуальную структуру объекта данных. Следующий <xref:System.Windows.DataTemplate> довольно прост. Мы предоставляем инструкции о том, что каждый элемент отображается в виде трех <xref:System.Windows.Controls.TextBlock> элементов в <xref:System.Windows.Controls.StackPanel>. Каждый элемент <xref:System.Windows.Controls.TextBlock> привязан к свойству класса `Task`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Базовые данные для примеров в этом разделе представляют собой коллекцию объектов CLR. Если выполнить привязку к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], основные понятия схожи, но есть незначительные синтаксические различия. Например, вместо `Path=TaskName`необходимо задать для параметра <xref:System.Windows.Data.Binding.XPath%2A> значение `@TaskName` (если `TaskName` является атрибутом узла [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]).  
  
 Теперь наш <xref:System.Windows.Controls.ListBox> выглядит следующим образом:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Создание шаблона DataTemplate как ресурса  
 В приведенном выше примере мы определили <xref:System.Windows.DataTemplate> встроенные. Обычно его определяют в разделе ресурсов, чтобы его можно было повторно использовать, как в следующем примере:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Теперь вы можете использовать `myTaskTemplate` в качестве ресурса, как показано в следующем примере:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Так как `myTaskTemplate` является ресурсом, теперь его можно использовать в других элементах управления, имеющих свойство, принимающее тип <xref:System.Windows.DataTemplate>. Как показано выше, для <xref:System.Windows.Controls.ItemsControl> объектов, таких как <xref:System.Windows.Controls.ListBox>, это свойство <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>. Для <xref:System.Windows.Controls.ContentControl> объектов это свойство <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Свойство DataType  
 Класс <xref:System.Windows.DataTemplate> имеет свойство <xref:System.Windows.DataTemplate.DataType%2A>, которое очень похоже на свойство <xref:System.Windows.Style.TargetType%2A> класса <xref:System.Windows.Style>. Поэтому вместо указания `x:Key` для <xref:System.Windows.DataTemplate> в приведенном выше примере можно выполнить следующие действия.  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Этот <xref:System.Windows.DataTemplate> применяется автоматически ко всем объектам `Task`. Обратите внимание, что в этом случае `x:Key` устанавливается неявно. Таким образом, если присвоить этому <xref:System.Windows.DataTemplate> значение `x:Key`, вы переопределяете неявное `x:Key`, а <xref:System.Windows.DataTemplate> не будет применяться автоматически.  
  
 При привязке <xref:System.Windows.Controls.ContentControl> к коллекции объектов `Task`, <xref:System.Windows.Controls.ContentControl> не использует описанные выше <xref:System.Windows.DataTemplate> автоматически. Это обусловлено тем, что для привязки <xref:System.Windows.Controls.ContentControl> требуются дополнительные сведения, чтобы определить, нужно ли выполнять привязку к целой коллекции или к отдельным объектам. Если <xref:System.Windows.Controls.ContentControl> отслеживает выбор типа <xref:System.Windows.Controls.ItemsControl>, можно задать для свойства <xref:System.Windows.Data.Binding.Path%2A> привязки <xref:System.Windows.Controls.ContentControl> значение "`/`", чтобы указать, что вы заинтересованы в текущем элементе. Для примера см. [Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). В противном случае необходимо явно указать <xref:System.Windows.DataTemplate>, задав свойство <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.  
  
 Свойство <xref:System.Windows.DataTemplate.DataType%2A> особенно полезно при наличии <xref:System.Windows.Data.CompositeCollection> различных типов объектов данных. Пример см. в разделе [Реализация CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Добавление дополнительных данных в DataTemplate  
 В настоящее время данные содержат необходимую информацию, но определенно это можно улучшить. Давайте улучшаем презентацию, добавляя <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>и некоторые <xref:System.Windows.Controls.TextBlock> элементы, описывающие отображаемые данные.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 На следующем снимке экрана показаны <xref:System.Windows.Controls.ListBox> с этим измененным <xref:System.Windows.DataTemplate>:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Можно задать для <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> на <xref:System.Windows.Controls.ListBox>, чтобы ширина элементов занимала все пространство:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Если для свойства <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> задано значение <xref:System.Windows.HorizontalAlignment.Stretch>, <xref:System.Windows.Controls.ListBox> теперь выглядит следующим образом:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Использование триггеров данных для применения значений свойств  
 В настоящей презентации не говорится о том, является ли `Task` домашней задачей или офисной. Помните, что объект `Task` имеет свойство `TaskType` типа `TaskType`, который является перечислением со значениями `Home` и `Work`.  
  
 В следующем примере <xref:System.Windows.DataTrigger> задает для <xref:System.Windows.Controls.Border.BorderBrush%2A> элемента с именем `border` значение `Yellow`, если свойство `TaskType` имеет значение `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Наше приложение теперь выглядит следующим образом. Домашние задачи отображаются с желтой границей, а офисные — с синей границей:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 В этом примере <xref:System.Windows.DataTrigger> использует <xref:System.Windows.Setter> для задания значения свойства. Классы триггеров также имеют свойства <xref:System.Windows.TriggerBase.EnterActions%2A> и <xref:System.Windows.TriggerBase.ExitActions%2A>, позволяющие запускать набор действий, таких как анимация. Кроме того, существует также <xref:System.Windows.MultiDataTrigger> класс, позволяющий применять изменения на основе нескольких значений свойств, привязанных к данным.  
  
 Другой способ добиться того же результата — привязать свойство <xref:System.Windows.Controls.Border.BorderBrush%2A> к свойству `TaskType` и использовать преобразователь значений для возврата цвета на основе значения `TaskType`. Создание вышеупомянутого эффекта с помощью преобразователя является немного более эффективным с точки зрения производительности. Кроме того, создание собственных преобразователей обеспечивает большую гибкость, так как вы предоставляете свою собственную логику. В конечном счете выбор техники зависит от сценария и предпочтений. Дополнительные сведения о создании преобразователя см. в разделе <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Что входит в DataTemplate?  

В предыдущем примере мы поместили триггер в <xref:System.Windows.DataTemplate> с помощью <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> . <xref:System.Windows.Setter> триггера задает значение свойства элемента (элемент <xref:System.Windows.Controls.Border>), находящиеся в пределах <xref:System.Windows.DataTemplate>. Однако если свойства, с которыми связаны `Setters`, не являются свойствами элементов, находящихся в текущем <xref:System.Windows.DataTemplate>, может быть удобнее задать свойства с помощью <xref:System.Windows.Style>, предназначенного для класса <xref:System.Windows.Controls.ListBoxItem> (если элемент управления, к которому выполняется привязка, является <xref:System.Windows.Controls.ListBox>). Например, если требуется, чтобы <xref:System.Windows.Trigger> анимировать <xref:System.Windows.UIElement.Opacity%2A> значение элемента при наведении указателя мыши на элемент, необходимо определить триггеры в <xref:System.Windows.Controls.ListBoxItem> стиле. Пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).
  
 В общем случае следует помнить, что <xref:System.Windows.DataTemplate> применяется к каждому из созданных <xref:System.Windows.Controls.ListBoxItem> (Дополнительные сведения о том, как и где она применяется, см. на странице <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.). <xref:System.Windows.DataTemplate> касается только представления и внешнего вида объектов данных. В большинстве случаев все остальные аспекты презентации, например то, как выглядит элемент, когда он выбран, или как <xref:System.Windows.Controls.ListBox> размещает элементы, не принадлежат в определении <xref:System.Windows.DataTemplate>. Пример см. в разделе [Стилизация и использование шаблонов для ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Выбор DataTemplate на основе свойств объекта данных  
 В разделе [Свойство DataType](#Styling_DataType) мы говорили о том, что можно определить различные шаблоны данных для различных объектов данных. Это особенно удобно при наличии <xref:System.Windows.Data.CompositeCollection> различных типов или коллекций с элементами различных типов. В разделе [Использование триггеров данных для применения значений свойств](#DataTrigger_to_Apply_Property_Values) мы показали, что если у вас есть коллекция объектов, имеющих одинаковый тип, можно создать <xref:System.Windows.DataTemplate>, а затем использовать триггеры для применения изменений на основе значений свойств каждого объекта данных. Тем не менее, хотя триггеры позволяют применить значения свойств или запустить анимацию, они не предоставляют гибкость, достаточную для реконструкции структуры объектов данных. Для некоторых сценариев может потребоваться создать разные <xref:System.Windows.DataTemplate> для объектов данных одного типа, но с разными свойствами.  
  
 Например, если объект `Task` имеет значение `Priority` свойства `1`, вы можете задать совершенно другой вид для него, чтобы сделать его сигналом оповещения. В этом случае вы создадите <xref:System.Windows.DataTemplate> для просмотра объектов с высоким приоритетом `Task`. Добавим следующий <xref:System.Windows.DataTemplate> в раздел Resources:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Обратите внимание, что в этом примере используется <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> . Ресурсы, определенные в этом разделе, совместно используются элементами в <xref:System.Windows.DataTemplate>.  
  
 Чтобы предоставить логику для выбора <xref:System.Windows.DataTemplate>, которая будет использоваться на основе значения `Priority` объекта данных, создайте подкласс <xref:System.Windows.Controls.DataTemplateSelector> и переопределите метод <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>. В следующем примере метод <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> предоставляет логику для возврата соответствующего шаблона на основе значения свойства `Priority`. Возвращаемый шаблон находится в ресурсах элемента <xref:System.Windows.Window> запечатывание.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Затем можно объявить `TaskListDataTemplateSelector` как ресурс:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Чтобы использовать ресурс селектора шаблона, назначьте его свойству <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> <xref:System.Windows.Controls.ListBox>. <xref:System.Windows.Controls.ListBox> вызывает метод <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> `TaskListDataTemplateSelector` для каждого элемента в базовой коллекции. Вызов передает объект данных в качестве параметра элемента. Затем <xref:System.Windows.DataTemplate>, возвращаемый методом, применяется к этому объекту данных.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 С помощью селектора шаблона <xref:System.Windows.Controls.ListBox> теперь выглядит следующим образом:  
  
 ![Снимок экрана образца шаблонов данных](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Это заключительный шаг нашего обсуждения данного примера. Полный пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Стилизация и использование шаблонов для ItemsControl  
 Несмотря на то, что <xref:System.Windows.Controls.ItemsControl> не единственный тип элемента управления, с помощью которого можно использовать <xref:System.Windows.DataTemplate>, это очень распространенный сценарий привязки <xref:System.Windows.Controls.ItemsControl> к коллекции. В разделе [что входит в DataTemplate](#what_belongs_in_datatemplate) мы обсуждали, что определение <xref:System.Windows.DataTemplate> должно быть связано только с представлением данных. Чтобы узнать, когда не подходит использовать <xref:System.Windows.DataTemplate>, важно понимать различные свойства стиля и шаблона, предоставляемые <xref:System.Windows.Controls.ItemsControl>. Следующий пример предназначен для демонстрации функции каждого из этих свойств. <xref:System.Windows.Controls.ItemsControl> в этом примере привязан к той же коллекции `Tasks`, что и в предыдущем примере. Для демонстрационных целей все стили и шаблоны в этом примере объявлены встроенными.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Ниже приведен снимок экрана примера при его просмотре:  
  
 ![Снимок экрана примера ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Обратите внимание, что вместо использования <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>можно использовать <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Пример см. в предыдущем разделе. Аналогично, вместо использования <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>можно использовать <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Два других свойства <xref:System.Windows.Controls.ItemsControl>, которые не показаны здесь, <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> и <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Поддержка иерархических данных  
 Пока мы только рассматривали как привязывать и отображать одну коллекцию. Иногда встречается коллекция, содержащая другие коллекции. Класс <xref:System.Windows.HierarchicalDataTemplate> предназначен для использования с типами <xref:System.Windows.Controls.HeaderedItemsControl> для вывода таких данных. В следующем примере `ListLeagueList` является списком объектов `League`. Каждый объект `League` содержит `Name` и коллекцию объектов `Division`. Каждый `Division` содержит `Name` и коллекцию объектов `Team`, и каждый объект `Team` содержит `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 В примере показано, что при использовании <xref:System.Windows.HierarchicalDataTemplate>можно легко отображать данные списка, содержащие другие списки. Ниже приведен снимок экрана примера.  
  
 ![Снимок экрана образца HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>См. также

- [Привязка данных](../advanced/optimizing-performance-data-binding.md)
- [Поиск элементов, созданных с использованием шаблона DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Стилизация и использование шаблонов](../controls/styling-and-templating.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о стилях заголовков столбцов GridView и шаблонах](../controls/gridview-column-header-styles-and-templates-overview.md)
