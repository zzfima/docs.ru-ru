---
title: Общие сведения о привязке данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data conversion for binding [WPF]
- binding data [WPF], about data binding
- data binding [WPF], about data binding
- conversion for data binding [WPF]
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
ms.openlocfilehash: 44a35131273c6f191ab5da5bc1639d97bd961ff1
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567517"
---
# <a name="data-binding-overview"></a>Общие сведения о привязке данных
Привязка данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет приложениям простой и последовательный способ представления данных и взаимодействия с ними. Элементы могут быть привязаны к данным из различных источников данных в форме объектов среды CLR и [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]. <xref:System.Windows.Controls.ContentControl>такие как <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.ItemsControl>, такие <xref:System.Windows.Controls.ListBox> как<xref:System.Windows.Controls.ListView> и, имеют встроенные функции для обеспечения гибкого стиля отдельных элементов данных или коллекций элементов данных. Представления сортировки, фильтрации и группировки могут быть организованы поверх данных.  
  
 Функции привязки данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют несколько преимуществ перед традиционными моделями, включая широкий диапазон свойств, которые внутренне поддерживают привязку данных, гибкое представление данных [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и четкое разделение бизнес-логики и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 В этом разделе сначала обсуждаются основные понятия [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] привязки данных, а затем рассматривается использование <xref:System.Windows.Data.Binding> класса и другие функции привязки данных.  

<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>Понятие привязки данных  
 Привязка данных — это процесс установки соединения между [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения и бизнес-логикой. Если для привязки заданы правильные настройки, а изменения значений данных сопровождаются правильными уведомлениями, привязанные к данным элементы автоматически отражают изменения. Привязка данных может также означать, что, если внешнее представление данных в элементе изменяется, то базовые данные могут автоматически обновляться для отражения изменений. Например, если пользователь редактирует значение в <xref:System.Windows.Controls.TextBox> элементе, базовое значение данных автоматически обновляется в соответствии с этим изменением.  
  
 Привязка к данным обычно используется для того, чтобы поместить серверный или локальные данные конфигурации в формы или другие элементы управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эта концепция расширяется и уже включает привязку широкого диапазона свойств к различным источникам данных. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]свойства зависимостей элементов могут быть привязаны к объектам CLR (включая объекты ADO.NET или объекты, связанные с веб-службами и веб-свойствами [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ) и данными.  
  
 Привязку данных можно рассмотреть на примере следующего [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения со страницы [примера привязки данных](https://go.microsoft.com/fwlink/?LinkID=163703).  
  
 ![Снимок экрана образца привязки данных](./media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 Выше приведен [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения, который отображает список лотов аукциона. Приложение демонстрирует следующие возможности привязки данных.  
  
- Содержимое <xref:System.Windows.Controls.ListBox> объекта привязано к коллекции объектов *AuctionItem* . Объект *AuctionItem* имеет такие свойства, как *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* и т. д.  
  
- Данные (объекты*AuctionItem* ) отображаются в <xref:System.Windows.Controls.ListBox> шаблоне, чтобы для каждого элемента отображалось описание и текущая цена. Это делается с помощью <xref:System.Windows.DataTemplate>. Кроме того, внешний вид каждого элемента зависит от значения *SpecialFeatures* отображаемого объекта *AuctionItem*. Если значением *SpecialFeatures* объекта *AuctionItem* является *Color*, элемент имеет синюю границу. Если значением является *Highlight*, элемент имеет оранжевые границы и помечается звездочкой. Раздел [Создание шаблонов данных](#data_templating) содержит сведения о создании шаблонов данных.  
  
- Пользователь может группировать, фильтровать или сортировать данные с помощью <xref:System.Windows.Controls.CheckBox>предоставленных объектов ES. На рисунке выше выбран параметр "Группировать по категории" и "Сортировать по категориям и датам" <xref:System.Windows.Controls.CheckBox>. Можно увидеть, что данные группируются по категориям продуктов, а имена категорий приводятся в алфавитном порядке. Из рисунка трудно заметить, что элементы в каждой категории также сортируются по начальной дате. Это делается с помощью *представления коллекции*. Представления коллекций рассматриваются в разделе [Привязка к коллекциям](#binding_to_collections).  
  
- Когда пользователь выбирает элемент, <xref:System.Windows.Controls.ContentControl> отображает подробные сведения о выбранном элементе. Это называется *Сценарий привязки "основной-подробности"* . Сведения об этом типе скрипта привязки см. в разделе [Сценарий привязки "основной-подробности"](#master_detail_scenario).  
  
- Типом свойства *StartDate* является <xref:System.DateTime>, который возвращает дату, которая включает время до миллисекунды. В этом приложении пользовательский преобразователь использовался для отображения даты в укороченном формате. Сведения о преобразователях см. в разделе [Преобразование данных](#data_conversion).  
  
 При нажатии кнопки *Добавить продукт* появляется следующая форма.  
  
 ![Добавить страницу списка продуктов](./media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 Пользователь может изменить поля формы, просмотреть список продуктов с помощью панелей краткого предварительного просмотра и подробного предварительного просмотра и нажать кнопку *Отправить*, для добавления данных нового продукта. К новой записи будут применимы все существующие функциональные возможности группировки, фильтрации и сортировки. В этом конкретном случае элемент, введенный на приведенном выше рисунке, будет отображаться как второй элемент в категории *Компьютер*.  
  
 Не показано на этом рисунке, — это логика проверки, указанная в *дате* <xref:System.Windows.Controls.TextBox>начала. Если пользователь вводит недопустимую дату (недопустимое форматирование или Дата окончания), пользователь будет уведомлен с <xref:System.Windows.Controls.ToolTip> помощью и красным восклицательным знаком рядом <xref:System.Windows.Controls.TextBox>с. Сведения о создании логики проверки см. в разделе [Проверка данных](#data_validation).  
  
 Прежде чем перейти к другим описанным выше возможностям связывания данных, в следующем разделе обсудим основные понятия, важные для понимания привязки данных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="basic-data-binding-concepts"></a>Основные понятия привязки данных  
  
 Независимо от того, какой элемент привязывается и какой источник данных используется, каждая привязка всегда соответствует модели, показанной на следующем рисунке.  
  
 ![Схема, на которой показана базовая модель привязки данных.](./media/data-binding-overview/basic-data-binding-diagram.png)  
  
 Как показано на приведенном выше рисунке, привязка данных является по существу мостом между целью привязки и источником привязки. На рисунке представлены следующие основные концепции привязки данных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Как правило, каждая привязка имеет четыре компонента: объект цели привязки, свойство цели, источник привязки и путь к значению используемого источника привязки. Например <xref:System.Windows.Controls.TextBox> , если требуется привязать содержимое к свойству *Name* объекта *Employee* <xref:System.Windows.Controls.TextBox>, целевой объект будет иметь значение, свойство Target — <xref:System.Windows.Controls.TextBox.Text%2A> это свойство, используемое значение — *имя*, а исходный объект является объектом *Employee* .  
  
- Целевое свойство должно быть свойством зависимостей. Большинство <xref:System.Windows.UIElement> свойств являются свойствами зависимостей и большинством свойств зависимостей, кроме доступных только для чтения, поддерживают привязку данных по умолчанию. (Только <xref:System.Windows.DependencyObject> типы могут определять свойства зависимостей, а <xref:System.Windows.UIElement>все они являются производными от <xref:System.Windows.DependencyObject>.)  
  
- Хотя это и не указано на рисунке, следует отметить, что объект источника привязки не может быть пользовательским объектом CLR. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Привязка данных поддерживает данные в виде объектов CLR и [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Чтобы предоставить несколько примеров, источником привязки может быть <xref:System.Windows.UIElement>, любой объект списка, объект CLR, связанный с ADO.NET данными или веб-службами, или XmlNode, содержащий ваши [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данные. Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](binding-sources-overview.md).  
  
 По мере прочтения в других разделах SDK важно помнить, что при создании привязки целевой объект привязки привязывается *к* источнику привязки. Например, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] при отображении некоторых базовых данных <xref:System.Windows.Controls.ListBox> в с помощью привязки данных вы привязываете <xref:System.Windows.Controls.ListBox> к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данным.  
  
 Чтобы установить привязку, используйте <xref:System.Windows.Data.Binding> объект. В оставшейся части этого раздела обсуждаются многие из концепций, связанных с, а также некоторые свойства и использование <xref:System.Windows.Data.Binding> объекта.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>Направление потока данных  
 Как упоминалось ранее и как указано стрелкой на рисунке выше, поток данных привязки может проходить от целевого объекта привязки к источнику привязки (например, значение Source изменяется, когда пользователь редактирует значение a <xref:System.Windows.Controls.TextBox>) и (или) из источника привязки. к цели привязки (например, <xref:System.Windows.Controls.TextBox> содержимое обновляется с учетом изменений в источнике привязки), если источник привязки предоставляет соответствующие уведомления.  
  
 Возможно, требуется, чтобы в приложении пользователи могли изменить данные и передать их обратно объекту источника. Или может потребоваться не предоставлять пользователям возможности обновления источника данных. Это можно контролировать, задав <xref:System.Windows.Data.Binding.Mode%2A> свойство <xref:System.Windows.Data.Binding> объекта. На следующем рисунке показаны различные типы потоков данных.  
  
 ![Поток данных привязки данных](./media/databinding-dataflow.png "DataBinding_DataFlow")  
  
- <xref:System.Windows.Data.BindingMode.OneWay>Привязка приводит к изменению свойства Source для автоматического обновления целевого свойства, но изменения целевого свойства не распространяются обратно в свойство Source. Этот тип привязки подходит, если привязываемый элемент управления неявно доступен только для чтения. Например, можно привязаться к источнику, такому как биржевые сводки, или, возможно, свойство цели не имеет интерфейса для внесения изменений, например цвета фона привязанной к данным таблицы. Если нет необходимости отслеживать изменения целевого свойства, можно работать в режиме привязки <xref:System.Windows.Data.BindingMode.OneWay> — в этом случае удастся избежать издержек режима привязки <xref:System.Windows.Data.BindingMode.TwoWay>.  
  
- <xref:System.Windows.Data.BindingMode.TwoWay>Привязка вызывает изменение либо свойства источника, либо целевого свойства для автоматического обновления другого. Этот тип привязки подходит для изменяемых форм или других полностью интерактивных сценариев [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Большинство свойств по умолчанию <xref:System.Windows.Data.BindingMode.OneWay> привязывается, но некоторые свойства зависимости (обычно свойства элементов управления, изменяемых пользователем, таких <xref:System.Windows.Controls.TextBox.Text%2A> как <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> свойство класса <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.TextBox> и свойство класса) по умолчанию имеютзначение<xref:System.Windows.Data.BindingMode.TwoWay> привязка. Существует способ определить программно, использует ли свойство зависимостей односторонние или двухсторонние привязки по умолчанию: для этого нужно получить метаданные этого свойства, воспользовавшись методом <xref:System.Windows.DependencyProperty.GetMetadata%2A>, а затем проверить логическое значение свойства <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource>является обратным <xref:System.Windows.Data.BindingMode.OneWay> привязкой; он обновляет свойство Source при изменении целевого свойства. Одним из примеров является пересчет исходного значения из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
- На рисунке <xref:System.Windows.Data.BindingMode.OneTime> не показана привязка, в результате чего свойство Source инициализирует целевое свойство, но последующие изменения не распространяются. Это означает, что, если в контексте данных производятся изменения или меняется объект, это изменение не отражается в целевом свойстве. Этот тип привязки подходит при использовании данных там, где приемлемо использовать снимок текущего состояния или данные действительно являются статичными. Этот тип привязки также является полезным, если нужно инициализировать целевое свойство с использованием какого-либо значения из исходного свойства, а контекст данных заранее неизвестен. Это, по сути, упрощенная форма привязки <xref:System.Windows.Data.BindingMode.OneWay>, которая обеспечивает более высокую производительность в случаях, когда исходное значение не меняется.  
  
 Обратите внимание, что для обнаружения изменений источника <xref:System.Windows.Data.BindingMode.OneWay> ( <xref:System.Windows.Data.BindingMode.TwoWay> применимо к привязкам и) источник должен реализовать подходящий механизм уведомления об <xref:System.ComponentModel.INotifyPropertyChanged>изменении свойств, например. Пример<xref:System.ComponentModel.INotifyPropertyChanged> реализации см. в разделе [Реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md) .  
  
 На <xref:System.Windows.Data.Binding.Mode%2A> странице свойств содержатся дополнительные сведения о режимах привязки и пример указания направления привязки.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>Что инициирует обновления источника  
 Привязки, которые <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource> ожидают изменения в целевом свойстве, и распространяют их обратно в источник. Это называется обновлением источника. Например, можно изменять текст элемента TextBox для изменения базового значение источника. Как описано в последнем разделе, направление потока данных определяется по значению <xref:System.Windows.Data.Binding.Mode%2A> свойства привязки.  
  
 Однако обновляется ли значение источника при изменении текста или после завершения изменения текста и отвода указателя мыши от элемента TextBox? <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Свойство привязки определяет, что активирует обновление источника. Точки на стрелках вправо на следующем рисунке иллюстрируют роль <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойства:  
  
 ![Схема, на которой показана роль свойства UpdateSourceTrigger.](./media/data-binding-overview/data-binding-updatesource-trigger.png)  
  
 Если значение равно <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, то значение, на которое указывает стрелка <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> вправо или привязки, обновляется сразу после изменения целевого свойства. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Однако если <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение равно <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, то это значение обновляется только с новым значением, когда целевое свойство теряет фокус.  
  
 Аналогично <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойству, различные свойства зависимостей имеют разные значения по умолчанию. <xref:System.Windows.Data.Binding.Mode%2A> Значение по умолчанию для большинства свойств зависимостей — <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, а свойство <xref:System.Windows.Controls.TextBox.Text%2A> имеет значение по умолчанию <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Это означает, что обновление источника обычно происходит при каждом изменении целевого свойства, что подходит для <xref:System.Windows.Controls.CheckBox>ES и других простых элементов управления. Однако для текстовых полей обновления после каждого нажатия клавиши уменьшают производительность и не дают пользователю обычной возможности удаления предыдущего символа и исправления ошибок ввода до того, как новое значение будет зафиксировано. Именно поэтому <xref:System.Windows.Controls.TextBox.Text%2A> свойство имеет <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> значение по умолчанию, а не <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 Сведения о <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> том, как найти значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> для свойства зависимостей, см. на странице свойств.  
  
 В следующей таблице приведен пример сценария для каждого <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значения с использованием в <xref:System.Windows.Controls.TextBox> качестве примера.  
  
|Значение UpdateSourceTrigger|Когда обновляется значение источника|Пример сценария для TextBox|  
|-------------------------------|----------------------------------------|----------------------------------|  
|Потеря фокуса ( <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>по умолчанию для)|Возникает при потере фокуса элементом управления TextBox|Объект <xref:System.Windows.Controls.TextBox> , связанный с логикой проверки (см. раздел Проверка данных)|  
|Свойство изменено|При вводе в<xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox>элементы управления в окне комнаты чата|  
|Явные|Когда приложение вызывает<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox>элементы управления в редактируемой форме (обновляет исходные значения только при нажатии пользователем кнопки "Отправить")|  
  
 Пример см. в разделе [Практическое руководство. Управление обновлением источника из поля TextBox](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>Создание привязки  
  
 Для рекапитулате некоторых концепций, обсуждаемых в предыдущих разделах, вы устанавливаете привязку с <xref:System.Windows.Data.Binding> помощью объекта, и каждая привязка обычно состоит из четырех компонентов: целевого объекта привязки, целевого свойства, источника привязки и пути к используемому исходному значению. Этот раздел описывает установку привязки.  
  
 Рассмотрим следующий пример, в котором объектом источника привязки является класс с именем *MyData*, определенный в пространстве имен *SDKSample*. В качестве демонстрационного примера класс *MyData* имеет строковое свойство с именем *ColorName* со значением Red. Таким образом, в этом примере создается кнопка с красным фоном.  
  
 [!code-xaml[BindNonTextProperty#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Дополнительные сведения о синтаксисе объявления привязки и примеры настройки привязки в коде см. в разделе [Общие сведения об объявлении привязок](binding-declarations-overview.md).  
  
 Если применить этот пример к основной диаграмме, полученное изображение будет выглядеть следующим образом. Это привязка, так как свойство Background поддерживает <xref:System.Windows.Data.BindingMode.OneWay> привязку по умолчанию. <xref:System.Windows.Data.BindingMode.OneWay>  
  
 ![Схема, показывающая свойство фона привязки данных.](./media/data-binding-overview/data-binding-button-background-example.png)  
  
 Может возникнуть вопрос, почему это работает даже несмотря на то, что свойство *colorname* имеет тип <xref:System.Windows.Controls.Control.Background%2A> String, а свойство <xref:System.Windows.Media.Brush>имеет тип. Это происходит в результате преобразования типов по умолчанию, которое обсуждается в разделе [Преобразование данных](#data_conversion).  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>Указание источника привязки  
 Обратите внимание, что в предыдущем примере источник привязки задается заданием <xref:System.Windows.FrameworkElement.DataContext%2A> свойства <xref:System.Windows.Controls.DockPanel> элемента. Затем класс наследует <xref:System.Windows.FrameworkElement.DataContext%2A> значение от <xref:System.Windows.Controls.DockPanel>, которое является его родительским элементом. <xref:System.Windows.Controls.Button> Повторим, что объект источника привязки является одним из четырех необходимых компонентов привязки. Таким образом, без указания объекта источника привязки эта привязка не имела бы смысла.  
  
 Есть несколько способов для указания объекта источника привязки. <xref:System.Windows.FrameworkElement.DataContext%2A> Использование свойства в родительском элементе полезно при привязке нескольких свойств к одному источнику. Однако иногда удобнее указывать источник привязки в отдельных объявлениях привязки. Для предыдущего примера вместо использования <xref:System.Windows.FrameworkElement.DataContext%2A> свойства можно указать источник привязки, <xref:System.Windows.Data.Binding.Source%2A> задав свойство непосредственно в объявлении привязки кнопки, как показано в следующем примере:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Кроме непосредственного задания <xref:System.Windows.FrameworkElement.DataContext%2A> свойства элемента, наследования <xref:System.Windows.FrameworkElement.DataContext%2A> значения из предка (например, кнопки в первом примере) и явного указания источника <xref:System.Windows.Data.Binding.Source%2A> привязки путем установки свойства в элементе <xref:System.Windows.Data.Binding> (например, кнопка последний пример), можно также использовать <xref:System.Windows.Data.Binding.ElementName%2A> свойство <xref:System.Windows.Data.Binding.RelativeSource%2A> или свойство, чтобы указать источник привязки. <xref:System.Windows.Data.Binding.ElementName%2A> Свойство полезно при привязке к другим элементам в приложении, например при использовании ползунка для настройки ширины кнопки. Свойство полезно, если привязка указана <xref:System.Windows.Controls.ControlTemplate> в или <xref:System.Windows.Style>. <xref:System.Windows.Data.Binding.RelativeSource%2A> Дополнительные сведения см. в разделе [Указание источника привязки](how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>Указание пути к значению  
 Если источником привязки является объект, используйте <xref:System.Windows.Data.Binding.Path%2A> свойство, чтобы указать значение, используемое для привязки. При привязке к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данным <xref:System.Windows.Data.Binding.XPath%2A> используйте свойство, чтобы указать значение. В некоторых случаях может быть применимо использование <xref:System.Windows.Data.Binding.Path%2A> свойства, даже если данные имеют [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]значение. Например, если требуется получить доступ к свойству Name возвращаемого XmlNode (в результате запроса XPath), следует использовать <xref:System.Windows.Data.Binding.Path%2A> свойство в дополнение <xref:System.Windows.Data.Binding.XPath%2A> к свойству.  
  
 Сведения о синтаксисе и примеры см. <xref:System.Windows.Data.Binding.Path%2A> на <xref:System.Windows.Data.Binding.XPath%2A> странице свойств и.  
  
 Обратите внимание, что хотя мы выделены, что <xref:System.Windows.Data.Binding.Path%2A> используемое значение является одним из четырех необходимых компонентов привязки, в сценариях, которые необходимо привязать ко всему объекту, используемое значение будет таким же, как и объект источника привязки. В таких случаях оно применимо не для указания <xref:System.Windows.Data.Binding.Path%2A>. Рассмотрим следующий пример.  
  
 [!code-xaml[MasterDetail#EmptyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 В приведенном выше примере используется синтаксис пустой привязки: {Binding}. В этом случае объект <xref:System.Windows.Controls.ListBox> наследует DataContext от родительского элемента DockPanel (не показан в этом примере). Если путь не указан, по умолчанию производится привязка ко всему объекту. Другими словами, в этом примере путь был оставлен, так как мы привязываете <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство ко всему объекту. (Подробное описание см. в разделе [Привязка к коллекциям](#binding_to_collections).)  
  
 Кроме привязки к коллекции, этот сценарий полезен также для привязки ко всему объекту, а не только к одному свойству объекта. Например, если объект источника является объектом строкового типа и всего лишь нужна привязка к самой строке. Другим распространенным сценарием является необходимость привязки элемента к объекту с несколькими свойствами.  
  
 Обратите внимание, что может потребоваться применить пользовательскую логику, чтобы данные имели смысл для свойства целевого объекта привязки. Пользовательская логика может иметь вид пользовательского преобразователя (если тип преобразования по умолчанию не существует). Сведения о преобразователях см. в разделе [Преобразование данных](#data_conversion).  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Привязка и класс BindingExpression  
 Прежде чем переходить к другим функциям и использованию привязки данных, можно было бы ввести <xref:System.Windows.Data.BindingExpression> класс. Как показано в предыдущих разделах, <xref:System.Windows.Data.Binding> класс является классом высокого уровня для объявления привязки <xref:System.Windows.Data.Binding> . класс предоставляет множество свойств, позволяющих задавать характеристики привязки. Связанный класс <xref:System.Windows.Data.BindingExpression>— это базовый объект, который поддерживает соединение между источником и целевым объектом. Привязка содержит всю информацию, которая может использоваться совместно в нескольких выражениях привязки. Представляет собой выражение экземпляра, которое не может быть общим и содержит все сведения об <xref:System.Windows.Data.Binding>экземпляре. <xref:System.Windows.Data.BindingExpression>  
  
 Например, рассмотрим следующее, где *myDataObject* — это экземпляр класса *MyData* , *myBinding* — исходный <xref:System.Windows.Data.Binding> объект, а класс *MyData* — это определенный класс, содержащий строковое свойство с именем  *MyDataProperty*. В этом примере выполняется привязка текстового содержимого *myText*, экземпляра <xref:System.Windows.Controls.TextBlock>, к *MyDataProperty*.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Один и тот же объект *myBinding* можно использовать для создания других привязок. Например, можно использовать объект *myBinding* для привязки текстового содержимого флажка к *MyDataProperty*. В этом сценарии будет два экземпляра <xref:System.Windows.Data.BindingExpression> , совместно использующих объект *myBinding* .  
  
 Объект можно получить с помощью возвращаемого значения вызова <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> для объекта, привязанного к данным. <xref:System.Windows.Data.BindingExpression> В следующих разделах демонстрируются некоторые способы использования <xref:System.Windows.Data.BindingExpression> класса:  
  
- [Практическое руководство. Получение объекта привязки из свойства целевого объекта привязки](how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
- [Практическое руководство. Управление обновлением источника из поля TextBox](how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>Преобразование данных  
 В предыдущем примере кнопка имеет красный цвет, так как ее <xref:System.Windows.Controls.Control.Background%2A> свойство привязано к строковому свойству со значением "Red". Это работает потому, что в <xref:System.Windows.Media.Brush> типе имеется преобразователь типов для преобразования строкового значения <xref:System.Windows.Media.Brush>в.  
  
 Если добавить эти сведения в рисунок из раздела [Создание привязки](#creating_a_binding), схема будет выглядеть следующим образом.  
  
 ![Схема, на которой показано свойство привязки данных по умолчанию.](./media/data-binding-overview/data-binding-button-default-conversion.png)  
  
 Однако что делать, если вместо свойства типа String у объекта источника привязки есть свойство *Color* типа <xref:System.Windows.Media.Color>? В этом случае для работы привязки необходимо сначала превратить значение свойства *Color* в то, что <xref:System.Windows.Controls.Control.Background%2A> принимает свойство. Необходимо создать пользовательский преобразователь, реализовав <xref:System.Windows.Data.IValueConverter> интерфейс, как показано в следующем примере:  
  
 [!code-csharp[ColorPicker_snip#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 Дополнительные сведения см. на справочнойстранице.<xref:System.Windows.Data.IValueConverter>  
  
 Теперь пользовательский преобразователь используется вместо преобразования по умолчанию и схема выглядит следующим образом.  
  
 ![Схема, на которой показан пользовательский преобразователь привязки данных.](./media/data-binding-overview/data-binding-converter-color-example.png)  
  
 Таким образом, преобразования по умолчанию могут быть доступны благодаря преобразователям типов, присутствующим в типе, к которому производится привязка. Такое поведение будет зависеть от того, какие преобразователи типов доступны в целевом объекте. Если существуют какие-то сомнением, создайте свой собственный преобразователь.  
  
 Ниже приведены некоторые типовые сценарии, где имеет смысл реализация преобразователя данных.  
  
- Данные должны отображаться по-разному в зависимости от региональных стандартов. Например, можно реализовать преобразователь валюты или преобразователь даты/времени в календаре на основе значений или стандартов, используемых в определенных региональных стандартах.  
  
- Используемые данные не обязательно предназначены для изменения текстового значения свойства, а предназначены для изменения некоторых других значений, например источника изображения, цвета или стиля отображаемого текста. Преобразователи могут использоваться в данном экземпляре для преобразования привязки неподходящего свойства, например привязки текстового поля к свойству Background ячейки таблицы.  
  
- К одним и тем же данным может быть привязано несколько элементов управления или несколько свойств элементов управления. В этом случае основная привязка может просто отображать текст, тогда как другие привязки обрабатывают специфичные проблемы отображения, но они по-прежнему используют одну и ту же привязку в качестве исходных данных.  
  
- Пока мы еще не обсуждали <xref:System.Windows.Data.MultiBinding>, где целевое свойство имеет коллекцию привязок. В случае с <xref:System.Windows.Data.MultiBinding>можно использовать пользовательский <xref:System.Windows.Data.IMultiValueConverter> объект для создания конечного значения из значений привязок. Например, цвет может быть вычислен из соотношения красного, синего и зеленого значений, которые могут быть значениями одних и тех же или разных объектов источника привязки. Примеры и <xref:System.Windows.Data.MultiBinding> сведения см. на странице классов.  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>Привязка к коллекциям  
  
 Объект источника привязки может рассматриваться как отдельный объект, свойства которого содержат данные, или как коллекция данных полиморфных объектов, часто группируемых вместе (например, в результате запроса к базе данных). Пока еще мы обсуждали привязку только к одному объекту, однако привязка к коллекции данных является распространенным сценарием. Например, распространенным сценарием <xref:System.Windows.Controls.ItemsControl> является использование <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>например, или <xref:System.Windows.Controls.TreeView> для отображения коллекции данных, например в приложении, показанном в разделе [что такое привязка данных?](#what_is_data_binding) .  
  
 К счастью, наша основная схема по-прежнему применима. При привязке <xref:System.Windows.Controls.ItemsControl> к коллекции схема выглядит следующим образом:  
  
 ![Схема, на которой показан объект ItemsControl привязки данных.](./media/data-binding-overview/data-binding-itemscontrol.png)  
  
 Как показано на этой схеме, для привязки <xref:System.Windows.Controls.ItemsControl> к объекту коллекции свойство является свойством, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> которое необходимо использовать. Можно представить себе <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство как содержимое <xref:System.Windows.Controls.ItemsControl>. Обратите внимание, что <xref:System.Windows.Data.BindingMode.OneWay> привязка выполняется <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> потому, <xref:System.Windows.Data.BindingMode.OneWay> что свойство поддерживает привязку по умолчанию.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>Способы реализации коллекций  
 Можно перечислять любую коллекцию, которая реализует <xref:System.Collections.IEnumerable> интерфейс. Однако, чтобы настроить динамические привязки таким образом, чтобы вставки или удаления в коллекции [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] автоматически обновляются, коллекция должна <xref:System.Collections.Specialized.INotifyCollectionChanged> реализовать интерфейс. Этот интерфейс предоставляет событие, которое должно вызываться при каждом изменении коллекции.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет класс, который является встроенной реализацией коллекции данных, <xref:System.Collections.Specialized.INotifyCollectionChanged> предоставляющей интерфейс. <xref:System.Collections.ObjectModel.ObservableCollection%601> Обратите внимание, что для полной поддержки передачи значений данных из исходных объектов в целевые объекты каждый объект в коллекции, который поддерживает связываемые свойства <xref:System.ComponentModel.INotifyPropertyChanged> , должен также реализовывать интерфейс. Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](binding-sources-overview.md).  
  
 Перед реализацией собственной коллекции рассмотрите возможность <xref:System.Collections.ObjectModel.ObservableCollection%601> использования или одного из существующих классов коллекций, таких как <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>и <xref:System.ComponentModel.BindingList%601>, между многими другими. Если у вас есть расширенный сценарий и вы хотите реализовать собственную коллекцию, рассмотрите возможность <xref:System.Collections.IList>использования, который предоставляет неуниверсальную коллекцию объектов, доступ к которой может осуществляться по отдельности по индексу и, таким образом, лучшая производительность.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>Представления коллекций  
 <xref:System.Windows.Controls.ItemsControl> После привязки к коллекции данных может потребоваться сортировка, фильтрация или группирование данных. Для этого используются представления коллекций, которые являются классами, реализующими <xref:System.ComponentModel.ICollectionView> интерфейс.  

#### <a name="what-are-collection-views"></a>Понятие о представлениях коллекций  
 Представление коллекции — это слой, расположенный в верхней части связанной исходной коллекции, с помощью которого можно перемещаться по исходной коллекции и просматривать ее содержимое на основе запросов сортировки, фильтрации и группировки, не изменяя саму коллекцию. В представлении коллекции также поддерживается указатель на текущий элемент коллекции. Если исходная коллекция реализует <xref:System.Collections.Specialized.INotifyCollectionChanged> интерфейс, то изменения, вызванные <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> этим событием, передаются в представления.  
  
 Так как представления не меняют базовые исходные коллекции, каждая исходная коллекция может иметь несколько связанных с ней представлений. Например, имеется коллекция объектов *Task*. С помощью представлений можно отображать одни и те же данные различными способами. Например, в левой части страницы можно отображать задачи, отсортированные по приоритету, а справа — сгруппированные по областям.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>Создание представления  
 Одним из способов создания и использования представления является непосредственное создание объекта представления и затем использование его в качестве источника привязки. В качестве примера рассмотрим приложение [Пример привязки данных](https://go.microsoft.com/fwlink/?LinkID=163703), показанное в подразделе [Понятие привязки данных](#what_is_data_binding). Приложение реализуется так, что <xref:System.Windows.Controls.ListBox> привязывается к представлению коллекции данных, а не к коллекции данных напрямую. Следующий пример извлекается из приложения [Пример привязки данных](https://go.microsoft.com/fwlink/?LinkID=163703). Класс является прокси класса, наследуемого от <xref:System.Windows.Data.CollectionView>. <xref:System.Windows.Data.CollectionViewSource> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] В этом конкретном примере <xref:System.Windows.Data.CollectionViewSource.Source%2A> представление привязано к коллекции *ауктионитемс* (типа <xref:System.Collections.ObjectModel.ObservableCollection%601>) текущего объекта приложения.  
  
 [!code-xaml[DataBindingLab#WindowResources1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 Затем ресурс *листингдатавиев* выступает в качестве источника привязки для элементов в приложении, например <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Чтобы создать другое представление для той же коллекции, можно создать другой <xref:System.Windows.Data.CollectionViewSource> экземпляр и присвоить ему другое `x:Key` имя.  
  
 В следующей таблице показано, какие типы данных представлений создаются как представление коллекции по умолчанию или <xref:System.Windows.Data.CollectionViewSource> на основе типа исходной коллекции.  
  
|Тип исходной коллекции|Тип представления коллекции|Примечания|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|Внутренний тип, основанный на<xref:System.Windows.Data.CollectionView>|Невозможно группировать элементы.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Самый быстрый.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>Использование представления по умолчанию  
 Один из способов создания и использования представления коллекции заключается в указании представления коллекции в качестве источника привязки. WPF также создает представление коллекции по умолчанию для каждой коллекции, используемой в качестве источника привязки. Если выполнить привязку непосредственно к коллекции, WPF выполняет привязку к представлению коллекции по умолчанию. Обратите внимание, что данное представление по умолчанию совместно используется всеми привязками к одной и той же коллекции, поэтому изменения, внесенные в представление по умолчанию одним привязанным элементом управления либо кодом (например, сортировка или изменение указателя на текущий элемент, что будет рассмотрено ниже), распространяются на все привязки к одной коллекции.  
  
 Чтобы получить представление по умолчанию, используйте <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> метод. Пример см. в разделе [Практическое руководство. Получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md).  
  
##### <a name="collection-views-with-adonet-datatables"></a>Использование представлений коллекций с таблицами данных ADO.NET  
 Чтобы повысить производительность, представления коллекций для ADO.NET <xref:System.Data.DataTable> или <xref:System.Data.DataView> объектов делегируют <xref:System.Data.DataView>сортировку и фильтрацию по отношению к. При этом функции сортировки и фильтрации совместно используются всеми представлениями коллекции для источника данных. Чтобы разрешить каждому представлению коллекции сортировку и фильтрацию независимо друг от друга, инициализируйте <xref:System.Data.DataView> каждое представление коллекции со своим собственным объектом.  
  
#### <a name="sorting"></a>Сортировка  
 Как уже отмечалось ранее, представления могут применять сортировку для коллекции. Так как данные находятся в базовой коллекции, они могут иметь или не иметь некий порядок следования. Представление коллекции позволяет установить порядок или изменить порядок, используемый по умолчанию, на основе введенных признаков сравнения. Так как это представление данных на стороне клиента, распространенным скриптом является сортировка пользователем столбцов табличных данных по значениям, содержащимся в столбце. С использованием представлений управляемая пользователем сортировка может применяться еще раз без необходимости внесения изменений в основную коллекцию или создания повторного запроса к содержимому коллекции. Пример см. в разделе [Практическое руководство. Сортировка столбцов GridView при нажатии на заголовок](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 В следующем примере показана логика сортировки приложения <xref:System.Windows.Controls.CheckBox> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] "Сортировать по категориям и дате" в разделе [что такое привязка данных?](#what_is_data_binding) .  
  
 [!code-csharp[DataBindingLab#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>Фильтрация  
 Представления могут применять к коллекции фильтр. Это означает, что несмотря на то что элемент может существовать в коллекции, его конкретное представление предназначено для отображения только некоторого подмножества полной коллекции. Возможна фильтрация по условию в данных. Например, как это делается в приложении в разделе [что такое привязка данных?](#what_is_data_binding) , "Показывать только расходы" <xref:System.Windows.Controls.CheckBox> содержит логику для фильтрации элементов, имеющих стоимость $25 или более. Следующий код выполняется для установки *шовонлибаргаинсфилтер* в качестве <xref:System.Windows.Data.CollectionViewSource.Filter> обработчика событий, <xref:System.Windows.Controls.CheckBox> когда он выбран:  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Обработчик события *ShowOnlyBargainsFilter* реализуется следующим образом.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Если вы используете один из <xref:System.Windows.Data.CollectionView> классов напрямую <xref:System.Windows.Data.CollectionViewSource>вместо <xref:System.Windows.Data.CollectionView.Filter%2A> , для указания обратного вызова следует использовать свойство. Пример см. в разделе [Практическое руководство. Фильтрация данных в представлении](how-to-filter-data-in-a-view.md).  
  
#### <a name="grouping"></a>Группирование  
 За исключением внутреннего класса, который просматривает <xref:System.Collections.IEnumerable> коллекцию, все представления коллекций поддерживают функции группирования, что позволяет пользователю секционировать коллекцию в представлении коллекции на логические группы. Группы могут быть явными, если пользователь предоставляет список групп, или неявными, если эти группы создаются динамически в зависимости от данных.  
  
 В следующем примере показана логика "Группировка по категории" <xref:System.Windows.Controls.CheckBox>:  
  
 [!code-csharp[DataBindingLab#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 Другой пример группировки см. в разделе [Практическое руководство. Группировка элементов в объекте ListView, реализующем GridView](../controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).  
  
#### <a name="current-item-pointers"></a>Указатели на текущий элемент  
 В представлениях также присутствует понятие текущего элемента. Существует возможность перемещаться по объектам в представлении коллекции. При переходе перемещается указатель элемента, позволяющий извлечь объект, расположенный в определенном месте в коллекции. Пример см. в разделе [Перемещение по объектам в Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
 Поскольку WPF выполняет привязку к коллекции только с помощью представления (либо указанного пользователем, либо представления коллекции по умолчанию), для всех привязок к коллекциям имеется указатель на текущий элемент. При привязке к представлению символ косой черты ("/") в значении `Path` указывает на текущий элемент представления. В следующем примере контекст данных является представлением коллекции. В первой строке выполняется привязка к коллекции. Во второй строке выполняется привязка к текущему элементу коллекции. В третьей строке выполняется привязка к свойству `Description` текущего элемента коллекции.  
  
```xaml  
<Button Content="{Binding }" />  
<Button Content="{Binding Path=/}" />  
<Button Content="{Binding Path=/Description}" />   
```  
  
 Косую черту и синтаксис свойства также можно комбинировать для обработки иерархии коллекций. В приведенном ниже примере выполняется привязка к текущему элементу коллекции `Offices`, который является свойством текущего элемента исходной коллекции.  
  
```xaml  
<Button Content="{Binding /Offices/}" />  
```  
  
 На указатель текущего элемента влияют примененные к коллекции операции сортировки и фильтрации. При сортировке указатель текущего элемента устанавливается на последний выбранный элемент, однако представление коллекции перестраивается относительно его. (Возможно, до этого выбранный элемент был в начале списка, но теперь выбранный элемент может оказаться где-нибудь в середине.) При фильтрации выбранный элемент сохраняется, если данный выбор остается в представлении после фильтрации. В противном случае указатель текущего элемента устанавливается на первый элемент отфильтрованного представления коллекции.  
  
<a name="master_detail_scenario"></a>   
#### <a name="master-detail-binding-scenario"></a>Сценарий "основной — подробности"  
 Понятие текущего элемента применимо не только для перемещения элементов в коллекции, но также для сценария привязки "основной — подробности". Еще раз рассмотрим [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения из подраздела [Понятие привязки данных](#what_is_data_binding). В этом приложении выбор в пределах <xref:System.Windows.Controls.ListBox> определяет содержимое, отображаемое <xref:System.Windows.Controls.ContentControl>в. Чтобы вставить <xref:System.Windows.Controls.ListBox> элемент другим способом, на <xref:System.Windows.Controls.ContentControl> странице отображаются подробные сведения о выбранном элементе.  
  
 Для реализации этого сценария необходимо наличие двух или более элементов управления, привязанных к одному и тому же представлению. В следующем примере из демонстрационного примера [привязки данных](https://go.microsoft.com/fwlink/?LinkID=163703) показана разметка <xref:System.Windows.Controls.ListBox> и в <xref:System.Windows.Controls.ContentControl> приложении [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , описанном в разделе [что такое привязка данных?](#what_is_data_binding) .  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Обратите внимание, что оба элемента управления привязаны к одному источнику, статическому ресурсу *listingDataView* (просмотреть определение этого ресурса можно в подразделе [Создание представления](#how_to_create_a_view)). Это работает потому, что когда одноэлементный <xref:System.Windows.Controls.ContentControl> объект (в данном случае) привязан к представлению коллекции, он автоматически привязывается <xref:System.Windows.Data.CollectionView.CurrentItem%2A> к представлению. Обратите <xref:System.Windows.Data.CollectionViewSource> внимание, что объекты автоматически синхронизируют валюту и выделены. Если элемент управления "список" не привязан к <xref:System.Windows.Data.CollectionViewSource> объекту, как в этом примере, необходимо установить его <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> свойство в `true` значение, чтобы это работало.  
  
 Другие примеры см. в разделах [Практическое руководство. Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) и [Практическое руководство. Использование шаблона "главный — подчиненный" с иерархическими данными](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Можно заметить, что в приведенном выше примере используется шаблон. Фактически, данные не будут отображаться так, как мы хотели бы без использования шаблонов (они явно используются в <xref:System.Windows.Controls.ContentControl> и неявно используются <xref:System.Windows.Controls.ListBox>). К шаблонам данных мы перейдем в следующем разделе.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>Шаблоны данных  
 Без использования шаблонов данных [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения в подразделе [Понятие привязки данных](#what_is_data_binding) будет выглядеть следующим образом.  
  
 ![Демонстрация привязки данных без шаблонов данных](./media/data-binding-overview/data-binding-demo-templates.png)  
  
 Как показано в примере в предыдущем разделе, <xref:System.Windows.Controls.ListBox> элементы управления <xref:System.Windows.Controls.ContentControl> и привязываются ко всему объекту коллекции (или, в частности, к представлению объекта коллекции) *AuctionItem*s. Без каких <xref:System.Windows.Controls.ListBox> -либо инструкций по отображению коллекции данных объект отображает строковое представление каждого объекта в базовой коллекции <xref:System.Windows.Controls.ContentControl> и отображает строковое представление объекта, к которому он привязан.  
  
 Чтобы решить эту проблему, приложение определяет <xref:System.Windows.DataTemplate>s. Как показано в примере в предыдущем разделе, в <xref:System.Windows.Controls.ContentControl> явном виде используется *детаилспродуктлистингтемплате*<xref:System.Windows.DataTemplate>. Элемент управления неявно использует следующие <xref:System.Windows.DataTemplate> объекты при отображении объектов *AuctionItem* в коллекции: <xref:System.Windows.Controls.ListBox>  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 Используя эти два <xref:System.Windows.DataTemplate>параметра, полученный пользовательский интерфейс будет показан в разделе [что такое привязка данных?](#what_is_data_binding) . Как видно из этого снимка экрана, помимо возможности размещения данных в элементах управления, <xref:System.Windows.DataTemplate>s позволяет определять привлекательные визуальные элементы для данных. Например <xref:System.Windows.DataTrigger>, s используется в приведенном выше <xref:System.Windows.DataTemplate> примере, чтобы *AuctionItem*s с *SpecialFeaturesным* *выделением* отображался с оранжевой границей и звездочкой.  
  
 Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](data-templating-overview.md).  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>Проверка данных  
  
 Для большинства приложений, принимающих входные данные от пользователя, необходима логика проверки, чтобы убедиться, что пользователь ввел ожидаемые данные. Проверка может основываться на типе, диапазоне, формате или других требованиях конкретного приложения. В этом разделе рассматривается, как работает проверка данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="associating-validation-rules-with-a-binding"></a>Связь правил проверки и привязки  
 Модель привязки <xref:System.Windows.Data.Binding.ValidationRules%2A> данных позволяет связать с <xref:System.Windows.Data.Binding> объектом. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Например, в следующем примере выполняется <xref:System.Windows.Controls.TextBox> привязка к свойству с именем `StartPrice` и <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> добавление <xref:System.Windows.Controls.ExceptionValidationRule> объекта в свойство.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 <xref:System.Windows.Controls.ValidationRule> Объект проверяет, является ли значение свойства допустимым. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]содержит два следующих типа встроенных <xref:System.Windows.Controls.ValidationRule> объектов:  
  
- <xref:System.Windows.Controls.ExceptionValidationRule> Проверяет исключения, возникающие во время обновления свойства источника привязки. В предыдущем примере `StartPrice` имеет тип integer. Когда пользователь вводит значение, которое невозможно преобразовать в целое число, создается исключение, приводящее к тому, что привязка будет помечена как недопустимая. <xref:System.Windows.Controls.ExceptionValidationRule> Альтернативный синтаксис для явной настройки заключается в `true` <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> присвоении свойству значения в <xref:System.Windows.Data.Binding> объекте <xref:System.Windows.Data.MultiBinding> или.  
  
- Объект проверяет наличие ошибок, вызванных объектами, которые <xref:System.ComponentModel.IDataErrorInfo> реализуют интерфейс. <xref:System.Windows.Controls.DataErrorValidationRule> Пример использования этого правила проверки см. в разделе <xref:System.Windows.Controls.DataErrorValidationRule>. <xref:System.Windows.Controls.DataErrorValidationRule> Альтернативный синтаксис для явной настройки заключается в `true` <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> присвоении свойству значения в <xref:System.Windows.Data.Binding> объекте <xref:System.Windows.Data.MultiBinding> или.  
  
 Можно также создать собственное правило проверки путем наследования от <xref:System.Windows.Controls.ValidationRule> класса и <xref:System.Windows.Controls.ValidationRule.Validate%2A> реализации метода. В следующем примере показано правило, используемое в списке "Дата начала" <xref:System.Windows.Controls.TextBox> , которое используется для *добавления продукта* в разделе [что такое привязка данных?](#what_is_data_binding) .  
  
 [!code-csharp[DataBindingLab#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 StartDateEntryForm<xref:System.Windows.Controls.TextBox> использует этот *футуредатеруле*, как показано в следующем примере:  
  
 [!code-xaml[DataBindingLab#CustomValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Обратите внимание, <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> что поскольку <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>значение равно, механизм привязки обновляет значение источника при каждом нажатии клавиши, что означает, что он также <xref:System.Windows.Data.Binding.ValidationRules%2A> проверяет каждое правило в коллекции при каждом нажатии клавиши. Это будет обсуждаться далее в разделе "Процесс проверки".  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>Предоставление визуального отклика  
 Если пользователь вводит недопустимое значение, можно сформировать отклик приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] на ошибку. Один из способов предоставить такую обратную связь — задать <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> для присоединенного свойства значение <xref:System.Windows.Controls.ControlTemplate>Custom. Как показано в предыдущем подразделе, *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> использует <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> вызываемую *валидатионтемплате*. В следующем примере показано определение элемента *validationTemplate*.  
  
 [!code-xaml[DataBindingLab#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 <xref:System.Windows.Controls.AdornedElementPlaceholder> Элемент указывает, где должен размещаться элемент управления.  
  
 Кроме того, можно также использовать <xref:System.Windows.Controls.ToolTip> для вывода сообщения об ошибке. Как *StartDateEntryForm* , так и *стартприцеентриформ*<xref:System.Windows.Controls.TextBox>ES используют стиль *textStyleTextBox*, который создает объект <xref:System.Windows.Controls.ToolTip> , отображающий сообщение об ошибке. В следующем примере показано определение элемента *textStyleTextBox*. Присоединенное свойство <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> возникает `true` , когда одна или несколько привязок в свойствах привязанного элемента имеют ошибку.  
  
 [!code-xaml[DataBindingLab#14](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 При возникновении ошибки проверки *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> будет выглядеть следующим образом: <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> <xref:System.Windows.Controls.ToolTip>  
  
 ![Ошибка проверки привязки данных](./media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 Если у <xref:System.Windows.Data.Binding> вас есть связанные правила проверки, но не <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> задано для привязанного элемента управления, будет <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> использоваться значение по умолчанию для уведомления пользователей об ошибке проверки. По умолчанию <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> используется шаблон элемента управления, определяющий красную границу на слое декоративных элементов. При ошибке <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> проверки значения <xref:System.Windows.Controls.ToolTip>по умолчанию и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для параметра *стартприцеентриформ* <xref:System.Windows.Controls.TextBox> выглядят следующим образом:  
  
 ![Ошибка проверки привязки данных](./media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 Пример предоставления логики проверки всех элементов управления в диалоговом окне см. в подразделе "Пользовательские диалоговые окна" раздела [Общие сведения о диалоговых окнах](../app-development/dialog-boxes-overview.md).  
  
### <a name="validation-process"></a>Процесс проверки  
 Проверка обычно выполняется, когда целевое значение передается свойству источника привязки. Это происходит в <xref:System.Windows.Data.BindingMode.TwoWay> привязках и <xref:System.Windows.Data.BindingMode.OneWayToSource> . Для повторного выполнения итерации, что приводит к тому, что обновление источника <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> зависит от значения свойства, как описано в разделе [что инициирует обновления источника](#what_triggers_source_updates) .  
  
 Ниже описан процесс *проверки*. Обратите внимание, что при возникновении ошибки проверки или ошибки другого типа на любом этапе данного процесса процесс будет прерван.  
  
1. Подсистема привязки проверяет <xref:System.Windows.Controls.ValidationRule> , <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> определены ли какие <xref:System.Windows.Data.Binding>-либо пользовательские объекты, для которых <xref:System.Windows.Controls.ValidationStep.RawProposedValue> задано значение. в этом случае он вызывает <xref:System.Windows.Controls.ValidationRule.Validate%2A> метод для каждого <xref:System.Windows.Controls.ValidationRule> , пока один из них не выполнит ошибку. или до тех пор, пока не будут пройдены все.  
  
2. Обработчик привязки вызывает преобразователь, если таковой существует.  
  
3. <xref:System.Windows.Controls.ValidationRule> Если преобразователь завершился успешно, подсистема привязки проверяет, <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> определены ли пользовательские объекты, <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> для <xref:System.Windows.Data.Binding>которых задано значение. в этом случае вызывается метод для каждого из <xref:System.Windows.Controls.ValidationRule.Validate%2A> <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> Задайтезначениедотехпор,покаодинизнихнезавершитсяошибкойили<xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> пока не будет пройден.  
  
4. Обработчик привязки присваивает значение исходному свойству.  
  
5. Подсистема привязки проверяет, <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> определены ли какие <xref:System.Windows.Data.Binding>-либо пользовательские объекты, для которых <xref:System.Windows.Controls.ValidationStep.UpdatedValue> задано значение. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> в этом случае вызывается <xref:System.Windows.Controls.ValidationRule.Validate%2A> метод для каждого <xref:System.Windows.Controls.ValidationRule> , для которого задано значение. <xref:System.Windows.Controls.ValidationStep.UpdatedValue> до тех пор, пока один из них не выполнит ошибку или пока не пройдет все. Если объект <xref:System.Windows.Controls.DataErrorValidationRule> связан с привязкой и для него <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> задано значение по умолчанию <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, <xref:System.Windows.Controls.DataErrorValidationRule> на этом этапе проверяется. Это также является точкой, когда проверяются привязки, <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> для `true` которых установлен флажок.  
  
6. Подсистема привязки проверяет, <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> определены ли какие <xref:System.Windows.Data.Binding>-либо пользовательские объекты, для которых <xref:System.Windows.Controls.ValidationStep.CommittedValue> задано значение. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> в этом случае вызывается <xref:System.Windows.Controls.ValidationRule.Validate%2A> метод для каждого <xref:System.Windows.Controls.ValidationRule> , для которого задано значение. <xref:System.Windows.Controls.ValidationStep.CommittedValue> до тех пор, пока один из них не выполнит ошибку или пока не пройдет все.  
  
 Если объект <xref:System.Windows.Controls.ValidationRule> не передается в какой-либо момент во время этого процесса, обработчик <xref:System.Windows.Controls.ValidationError> привязки создает объект <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> и добавляет его в коллекцию связанного элемента. Прежде чем обработчик привязки запустит <xref:System.Windows.Controls.ValidationRule> объекты на любом шаге, он удаляет все <xref:System.Windows.Controls.ValidationError> <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> , что было добавлено к присоединенному свойству связанного элемента на этом этапе. Например <xref:System.Windows.Controls.ValidationRule> , если для, для <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которого задано <xref:System.Windows.Controls.ValidationStep.UpdatedValue> значение Failed, в следующий раз при выполнении проверки механизм привязки удаляет <xref:System.Windows.Controls.ValidationError> его непосредственно перед вызовом Any <xref:System.Windows.Controls.ValidationRule> , <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> для которого задано значение. <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 Если <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> параметр не пуст <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> , присоединенное свойство элемента устанавливается в `true`значение. Кроме того, если <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> свойство <xref:System.Windows.Data.Binding> объекта имеет значение `true`, подсистема привязки вызывает <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> событие, присоединенное к элементу.  
  
 Также обратите внимание, что допустимое перемещение значения в любом направлении (цель к источнику или исходному объекту <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> ) очищает присоединенное свойство.  
  
 <xref:System.Windows.Controls.ExceptionValidationRule> Если привязка либо имеет связанную с ней <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> свойство, либо если свойству присвоено `true` значение, а исключение возникает, когда механизм привязки задает источник, механизм привязки проверяет наличие объекта. <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> Можно использовать <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> обратный вызов для предоставления пользовательского обработчика для обработки исключений. Если параметр не указан <xref:System.Windows.Data.Binding>в, подсистема привязки создает <xref:System.Windows.Controls.ValidationError> исключение и добавляет его в <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> коллекцию связанного элемента. <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>  
  
## <a name="debugging-mechanism"></a>Механизм отладки  
 Чтобы получить сведения о состоянии конкретной <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> привязки, можно задать присоединенное свойство объекта, связанного с привязкой.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Новые возможности в WPF версии 4.5](../getting-started/whats-new.md)
- [Привязка к результатам запроса LINQ](how-to-bind-to-the-results-of-a-linq-query.md)
- [Привязка данных](../advanced/optimizing-performance-data-binding.md)
- [Демонстрация привязки данных](https://go.microsoft.com/fwlink/?LinkID=163703)
- [Разделы практического руководства](data-binding-how-to-topics.md)
- [Привязка к источнику данных ADO.NET](how-to-bind-to-an-ado-net-data-source.md)
