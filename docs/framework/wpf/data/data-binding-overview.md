---
title: "Общие сведения о связывании данных | Microsoft Docs"
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
  - "привязка данных, сведения о привязке данных"
  - "преобразование для привязки данных"
  - "привязка данных, сведения о привязке данных"
  - "преобразование данных для привязки"
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
caps.latest.revision: 78
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 75
---
# Общие сведения о связывании данных
Привязка данных [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] обеспечивает простой и согласованный способ представления данных и взаимодействия с ними в приложениях.  Можно связывать элементы с данными из разнообразных источников данных в форме объектов [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] и [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  Элементы управления <xref:System.Windows.Controls.ContentControl>, например <xref:System.Windows.Controls.Button>, элементы управления <xref:System.Windows.Controls.ItemsControl>, например <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ListView> обладают встроенной возможностью включения гибких стилей для отдельных элементов данных и коллекций элементов данных.  Представления сортировки, фильтрации и группировки могут быть организованы поверх данных.  
  
 Функциональные возможности связывания данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют несколько преимуществ перед традиционными моделями, включая широкий диапазон свойств, которые внутренне поддерживают связывание данных, гибкое представление [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] данных и четкое разделение бизнес\-логики и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 В этом разделе сначала будут рассмотрены основные фундаментальные понятия связывания данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а затем — использование класса <xref:System.Windows.Data.Binding> и других возможностей связывания данных.  
  
   
  
<a name="what_is_data_binding"></a>   
## Понятие о привязке к данным  
 Привязка к данным является процессом, который устанавливает связь между приложением [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и бизнес\-логикой.  Если привязка имеет правильные параметры и данные предоставляют правильные уведомления, то при изменении значений данных в элементах, которые привязаны к данным, автоматически отражаются изменения.  Привязка к данным может также означать, что если внешнее представление данных в элементе изменяется, то базовые данные могут автоматически обновляться для отражения изменений.  Например если пользователь изменяет значение в элементе <xref:System.Windows.Controls.TextBox>, базовое значение данных автоматически обновляется, чтобы отразить это изменение.  
  
 Привязка к данным обычно используется для того, чтобы поместить сервер или локальную конфигурацию данных в формы или другие элементы управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эта концепция расширяется и уже включает привязку широкого диапазона свойств к различным источникам данных.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [свойства зависимостей](GTMT) элементов могут быть привязаны к объектам [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] \(включая объекты [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] или объекты, связанные с веб\-службами и веб\-свойствами\), и к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 Привязку данных можно рассмотреть на примере следующего приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]со страницы [Примера привязки данных \(содержимое страницы может отображаться на английском языке\)](http://go.microsoft.com/fwlink/?LinkID=163703):  
  
 ![Снимок экрана примера привязки данных](../../../../docs/framework/wpf/data/media/databinding-databindingdemo.png "DataBinding\_DataBindingDemo")  
  
 Выше показан интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения, который отображает список лотов аукциона.  Приложение демонстрирует следующие возможности связывания данных:  
  
-   Содержимое <xref:System.Windows.Controls.ListBox> привязано к коллекции объектов *AuctionItem*.  Объект *AuctionItem* имеет такие свойства как *Description* *StartPrice* *StartDate*, *Category*, *SpecialFeatures* и т.д.  
  
-   Данные \(объекты *AuctionItem*\), отображаемые в <xref:System.Windows.Controls.ListBox>, используются в шаблоне таким образом, что для каждого элемента показаны его описание и текущая цена.  Это делается с помощью <xref:System.Windows.DataTemplate>.  Кроме того, внешний вид каждого элемента зависит от значения*SpecialFeatures* отображаемого объекта *AuctionItem*.  Если значением *SpecialFeatures* объекта *AuctionItem* является *Color*, элемент имеет синюю границу.  Если значением является *Highlight*, элемент имеет оранжевые границы и помечается звездочкой.  Раздел [Создание шаблонов данных](#data_templating) содержит сведения о создании шаблонов данных.  
  
-   Пользователь может группировать, фильтровать или сортировать данные с помощью предоставленных элементов <xref:System.Windows.Controls.CheckBox>.  На рисунке, приведенном выше, выбраны элементы <xref:System.Windows.Controls.CheckBox> "Группировать по категориям" и "Сортировать по категориям и дате".  Обратите внимание, что данные группируются по категориям продуктов, а имена категорий приводятся в алфавитном порядке.  Из рисунка трудно заметить, что элементы в каждой категории также сортируются по начальной дате.  Это делается с использованием *представления коллекции*.  В разделе [Привязка к коллекциям](#binding_to_collections) обсуждаются представления коллекций.  
  
-   Когда пользователь выбирает элемент, <xref:System.Windows.Controls.ContentControl> отображает подробное описание выбранного элемента.  Это называется *Скрипт "основной\/подробности"*.  В разделе [Скрипт "основной\/подробности"](#master_detail_scenario) содержатся сведения об этом типе скрипта привязки.  
  
-   Типом свойства *StartDate* является <xref:System.DateTime>, который возвращает дату, включая время с точностью до миллисекунды.  В этом приложении пользовательский преобразователь был использован таким образом, чтобы дата отображалась в укороченном формате.  В разделе [Преобразование данных](#data_conversion) представлены сведения о преобразователях.  
  
 При нажатии кнопки *Добавить продукт*, появляется следующая форма:  
  
 ![Добавить страницу списка продуктов](../../../../docs/framework/wpf/data/media/databinding-demo-addproductlisting.png "DataBinding\_Demo\_AddProductListing")  
  
 Пользователь может изменить поля формы, просмотреть список продуктов с помощью панелей краткого предварительного просмотра и подробного предварительного просмотра и нажать кнопку *Отправить* для добавления данных нового продукта.  К новой записи будут применимы все существующие функциональные возможности группировки, фильтрации и сортировки.  В этом конкретном случае элемент, введенный на приведенном выше рисунке, будут отображаться как второй элемент в категории *Компьютер*.  
  
 На этом рисунке не показана логика проверки, предоставленная в <xref:System.Windows.Controls.TextBox>*Start Date*.  Если пользователь вводит недопустимую дату \(недопустимый формат или прошедшую дату\), он будет уведомлен <xref:System.Windows.Controls.ToolTip> и красным восклицательным знаком после <xref:System.Windows.Controls.TextBox>.  В разделе [Проверка данных](#data_validation) обсуждается создание логики проверки.  
  
 Прежде чем перейти в другим описанным выше возможностям связывания данных, в следующем разделе обсудим основные понятия, важные для понимания связывание данных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="basic_data_binding_concepts"></a>   
## Основные понятия связывания данных  
   
  
 Вне зависимости от того, каких элементы привязываются и какой источник данных используется, каждая привязка всегда соответствует модели, показанной на следующем рисунке:  
  
 ![Основная схема привязки данных](../../../../docs/framework/wpf/data/media/databindingmostbasic.png "DataBindingMostBasic")  
  
 Как показано в приведенном выше рисунке, связывание данных является по существу мостом между [целью привязки](GTMT) и [источником привязки](GTMT).  На рисунке представлены следующие основные концепции связывания данных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Обычно каждая привязка имеет четыре компонента: объект [цели привязки](GTMT), свойство цели, [источник привязки](GTMT) и путь к значению используемого [источника привязки](GTMT).  Например, если требуется связать содержимое <xref:System.Windows.Controls.TextBox> со свойством *Имя* объекта *Сотрудник*, объектом цели является <xref:System.Windows.Controls.TextBox>, свойством цели является свойство <xref:System.Windows.Controls.TextBox.Text%2A>, используемым значением является *Имя*, а объектом источника является объект *Сотрудник*.  
  
-   Свойством цели должно быть [свойство зависимостей](GTMT).  Большинство свойств <xref:System.Windows.UIElement> является [свойствами зависимостей](GTMT), а большинство [свойств зависимостей](GTMT), за исключением свойств, доступных только для чтения, по умолчанию поддерживает связывание данных.  \([Свойства зависимости](GTMT) можно определить только через типы <xref:System.Windows.DependencyObject>, а все элементы <xref:System.Windows.UIElement> производятся от <xref:System.Windows.DependencyObject>\).  
  
-   Хотя на рисунке это не показано, однако следует отметить, что объект [источника привязки](GTMT) не обязательно должен быть пользовательским объектом [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Привязка данных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает данные в форме объектов [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] и [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Например, источником привязки может быть <xref:System.Windows.UIElement>, любой объект списка, объект [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], связанный с данными [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] или веб\-службами, или узел XmlNode, содержащий данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 В процессе чтения других разделов [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] важно помнить, что при связывании [цель привязки](GTMT) *привязывается к* [источнику привязки](GTMT).  Например, при отображении некоторых базовых данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в <xref:System.Windows.Controls.ListBox> с использованием привязки данных, <xref:System.Windows.Controls.ListBox> привязывается к данным [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 Чтобы установить привязку, используйте объект <xref:System.Windows.Data.Binding>.  В остальной части этого раздела обсуждаются многие понятия, связанные с некоторыми свойствами и использованием объекта <xref:System.Windows.Data.Binding>.  
  
<a name="direction_of_data_flow"></a>   
### Направление потока данных  
 Как упоминалось ранее и как показывает стрелка на приведенном выше рисунке, поток данных связывания может идти от [цели привязки](GTMT) к [источнику привязки](GTMT) \(например, исходное значение изменяется, когда пользователь изменяет значение <xref:System.Windows.Controls.TextBox>\) и\/или от [источника привязки](GTMT) к [цели привязки](GTMT) \(например, содержимое <xref:System.Windows.Controls.TextBox> обновляется при изменениях в [источнике привязки](GTMT)\), если источник привязки предоставляет соответствующие уведомления.  
  
 Возможно, требуется, чтобы в приложении пользователи могли изменить данные и передать их обратно объекту источника.  Или может потребоваться не предоставлять пользователям возможности обновления источника данных.  Это можно регулировать с помощью свойства <xref:System.Windows.Data.Binding.Mode%2A> объекта <xref:System.Windows.Data.Binding>.  На следующем рисунке показаны различные типы потоков данных:  
  
 ![Поток данных привязки данных](../../../../docs/framework/wpf/data/media/databinding-dataflow.png "DataBinding\_DataFlow")  
  
-   Связывание <xref:System.Windows.Data.BindingMode> приводит к изменениям свойства источника для автоматического обновления свойства цели, но изменения свойства цели не передаются обратно к свойству источника.  Этот тип привязки подходит, если привязка элемента управления неявно доступна только для чтения.  Например, можно привязаться к источнику, такому как биржевые сводки, или, возможно, свойство цели не имеет интерфейса для внесения изменений, например цвета фона привязанной к данным таблицы.  Если отсутствует необходимость отслеживать изменения свойства цели, можно использовать режим привязки <xref:System.Windows.Data.BindingMode>, при котором удастся избежать издержек режима привязки <xref:System.Windows.Data.BindingMode>.  
  
-   Тип связывания <xref:System.Windows.Data.BindingMode> вызывает изменения либо свойства цели, либо свойства источника для автоматического обновления другого.  Этот тип привязки подходит для изменяемых форм или других полностью интерактивных скриптов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Большинство свойств являются свойствами по умолчанию для связывания <xref:System.Windows.Data.BindingMode>, но некоторые [свойства зависимостей](GTMT) \(обычно свойства изменяемых пользователями элементов управления, такие как свойство <xref:System.Windows.Controls.TextBox.Text%2A> элемента <xref:System.Windows.Controls.TextBox> и свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> элемента <xref:System.Windows.Controls.CheckBox>\) являются свойствами по умолчанию для связывания <xref:System.Windows.Data.BindingMode>.  Определить программный способом, связано ли по умолчанию [свойство зависимостей](GTMT) односторонним или двусторонним способом, можно, получив метаданные свойства с помощью <xref:System.Windows.DependencyProperty.GetMetadata%2A>, а затем проверив логическое значение свойства <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>.  
  
-   Связывание <xref:System.Windows.Data.BindingMode> является обратным к связыванию <xref:System.Windows.Data.BindingMode>; оно обновляет свойство источника при изменении свойства цели.  Одним примером скрипта является пересчет значения цели из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   На рисунке не показана привязка <xref:System.Windows.Data.BindingMode>, которая вызывает инициализацию свойства цели свойством источника, но последующие изменения при этом не распространяются.  Это означает, что, если в контексте данных производятся изменения или меняется объект, это изменение не отражается в целевом свойстве.  Этот тип привязки можно применять, если для использования данных подходит снимок или данные являются статическими.  Этот тип привязки также может использоваться, если необходимо инициализировать целевое свойство с некоторым значением из исходного свойства, и контекст данных не известен заранее.  По существу, это является простой формой связывания <xref:System.Windows.Data.BindingMode>, которая обеспечивает лучшую производительность в случаях, когда значение цели не изменяется.  
  
 Обратите внимание, что для обнаружения изменений в источнике \(применимо для связывания <xref:System.Windows.Data.BindingMode> и <xref:System.Windows.Data.BindingMode>\), источник должен реализовывать подходящий механизм уведомления об изменении свойства, такой как <xref:System.ComponentModel.INotifyPropertyChanged>.  Пример реализации класса <xref:System.ComponentModel.INotifyPropertyChanged> см. в разделе [Реализация уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 На странице свойства <xref:System.Windows.Data.Binding.Mode%2A> содержатся дополнительные сведения о режимах привязки и пример того, как указать направление привязки.  
  
<a name="what_triggers_source_updates"></a>   
### Что инициирует обновления источника  
 Привязки типов<xref:System.Windows.Data.BindingMode> и <xref:System.Windows.Data.BindingMode> отслеживают изменения свойства цели и передают их обратно к источнику.  Это называется обновлением источника.  Например, можно изменять текст элемента TextBox для изменения базового значение источника.  Как описано в последнем разделе, направление потока данных определяется значением свойства привязки <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 Однако обновляется ли значение источника при изменении текста или после завершения изменения текста и отвода указателя мыши от элемента TextBox?  Свойство <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> привязки определяет, что инициирует обновление источника.  Точки стрелок вправо на следующем рисунке показывают роль свойства <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>:  
  
 ![Схема UpdateSourceTrigger](../../../../docs/framework/wpf/data/media/databindingupdatesourcetrigger.png "DataBindingUpdateSourceTrigger")  
  
 Если значение элемента <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> равно <xref:System.Windows.Data.UpdateSourceTrigger>, значение, на которое указывает правая стрелка привязок <xref:System.Windows.Data.BindingMode> или <xref:System.Windows.Data.BindingMode>, обновляется сразу же после изменения свойства цели.  Однако если значение <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> равно <xref:System.Windows.Data.UpdateSourceTrigger>, значение обновляется только тогда, когда свойство цели теряет фокус.  
  
 Аналогично свойству <xref:System.Windows.Data.Binding.Mode%2A>, различные [свойства зависимостей](GTMT) имеют различные значения по умолчанию для <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  Значением по умолчанию для большинства [свойств зависимостей](GTMT) является <xref:System.Windows.Data.UpdateSourceTrigger>, в то время как свойство<xref:System.Windows.Controls.TextBox.Text%2A> по умолчанию имеет значение <xref:System.Windows.Data.UpdateSourceTrigger>.  Это означает, что обновления цели обычно происходят при изменении свойства цели, что подходит для <xref:System.Windows.Controls.CheckBox> и других простых элементов управления.  Однако для текстовых полей обновления после каждого нажатия клавиши уменьшают производительность и не дают пользователю обычной возможности удаления предыдущего символа и исправления ошибок ввода до того, как новое значение будет зафиксировано.  Именно поэтому свойство <xref:System.Windows.Controls.TextBox.Text%2A> по умолчанию имеет значение <xref:System.Windows.Data.UpdateSourceTrigger> вместо <xref:System.Windows.Data.UpdateSourceTrigger>.  
  
 Сведения о том, как найти значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> [свойства зависимостей](GTMT), см. на странице свойства <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
 В следующей таблице представлены примеры скриптов для каждого значения <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>, использующие <xref:System.Windows.Controls.TextBox> как пример:  
  
|Значение UpdateSourceTrigger|Когда обновляется значение источника|Пример скрипта для TextBox|  
|----------------------------------|------------------------------------------|--------------------------------|  
|LostFocus \(значение по умолчанию для <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>\)|Возникает при потере фокуса элементом управления TextBox.|<xref:System.Windows.Controls.TextBox>, который связан с логикой проверки \(см. раздел "Проверка данных"\)|  
|PropertyChanged|При вводе в <xref:System.Windows.Controls.TextBox>|Элемент управления <xref:System.Windows.Controls.TextBox> в окне чата|  
|Explicit|Когда приложение вызывает <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|Элемент управления <xref:System.Windows.Controls.TextBox> в редактируемой форме \(обновляет значения источника только при нажатии пользователем кнопки отправки\)|  
  
 Пример см. в разделе [Управление обновлением источника из поля TextBox](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## Создание привязки  
   
  
 Подводя итог некоторым основным понятиям, описанным в предыдущих разделах, следует сказать, что связывание устанавливается с помощью объекта <xref:System.Windows.Data.Binding> и каждая привязка обычно состоит из четырех компонентов: цель привязки, свойство цели, источник привязки и путь к используемому значению источника.  Этот раздел описывает установку привязки.  
  
 Рассмотрим следующий пример, в котором объектом источника привязки является класс с именем *MyData*, определенный в пространстве имен *SDKSample*.  В качестве демонстрационного примера класс *MyData* имеет строковое свойство *ColorName*, установленное в значение "Красный".  Таким образом, этот пример создает кнопку с красным фоном.  
  
 [!code-xml[BindNonTextProperty#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Дополнительные сведения о синтаксисе объявления привязки и примеры настройки привязки в коде см. в разделе [Общие сведения об объявлении привязок](../../../../docs/framework/wpf/data/binding-declarations-overview.md).  
  
 Если применить этот пример к основной диаграмме, полученное изображение будет выглядеть следующим образом.  Это привязка <xref:System.Windows.Data.BindingMode>, так как свойство Background по умолчанию поддерживает привязку <xref:System.Windows.Data.BindingMode>.  
  
 ![Схема привязки данных](../../../../docs/framework/wpf/data/media/databindingbuttonbackgroundexample.png "DataBindingButtonBackgroundExample")  
  
 Может вызвать удивление, почему это работает, несмотря на то, что свойство *ColorName* — строковое, в то время как свойство <xref:System.Windows.Controls.Control.Background%2A> является свойством типа <xref:System.Windows.Media.Brush>.  Это происходит в результате преобразования типов по умолчанию, которое обсуждается в разделе [Преобразование данных](#data_conversion).  
  
<a name="specifying_the_binding_source"></a>   
### Указание источника привязки  
 Обратите внимание, что в предыдущем примере источник привязки определялся установкой свойства <xref:System.Windows.FrameworkElement.DataContext%2A> на элементе <xref:System.Windows.Controls.DockPanel>.  Затем <xref:System.Windows.Controls.Button> наследует значение <xref:System.Windows.FrameworkElement.DataContext%2A> от <xref:System.Windows.Controls.DockPanel>, являющегося его родительским элементом.  Повторим, что объект источника привязки является одним из четырех необходимых компонентов привязки.  Таким образом, без указания объекта источника привязки эта привязка не имела бы смысла.  
  
 Есть несколько способов для указания объекта источника привязки.  С помощью свойства <xref:System.Windows.FrameworkElement.DataContext%2A> родительского элемента удобно привязывать несколько свойств к одному источнику.  Однако иногда удобнее указывать источник привязки в отдельных объявлениях привязки.  В предыдущем примере вместо использования свойства <xref:System.Windows.FrameworkElement.DataContext%2A> можно указать источник привязки, установив свойство <xref:System.Windows.Data.Binding.Source%2A> непосредственно в объявлении привязки кнопки, как показано в следующем примере:  
  
 [!code-xml[BindNonTextProperty#BackgroundBindingCompact](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Кроме установки свойства <xref:System.Windows.FrameworkElement.DataContext%2A> непосредственно в элементе, наследования значения <xref:System.Windows.FrameworkElement.DataContext%2A> от предка \(как, например, кнопки в первом примере\) и явного указания источника привязки установкой свойства <xref:System.Windows.Data.Binding.Source%2A> на <xref:System.Windows.Data.Binding> \(например, кнопки в последнем примере\), можно также использовать свойство <xref:System.Windows.Data.Binding.ElementName%2A> или свойство <xref:System.Windows.Data.Binding.RelativeSource%2A> для указания источника привязки.  Свойство <xref:System.Windows.Data.Binding.ElementName%2A> полезно при связывании с другими элементами приложения, например при использовании ползунка для настройки ширины кнопки.  Свойство <xref:System.Windows.Data.Binding.RelativeSource%2A> используется при установке связывания в <xref:System.Windows.Controls.ControlTemplate> или <xref:System.Windows.Style>.  Дополнительные сведения см. в разделе [Указание источника привязки](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### Указание пути к значению  
 Если источник привязки является объектом, используйте свойство <xref:System.Windows.Data.Binding.Path%2A> для указания значения, используемого для привязки.  При связывании данных [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] используйте свойство <xref:System.Windows.Data.Binding.XPath%2A> для указания значения.  В некоторых случаях удобно применить свойство <xref:System.Windows.Data.Binding.Path%2A>, даже если это данные [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  Например, если требуется получить доступ к свойству "Имя" возвращаемого XmlNode \(в результате выполнения запроса XPath\), следует использовать свойство <xref:System.Windows.Data.Binding.Path%2A> в дополнении к свойству <xref:System.Windows.Data.Binding.XPath%2A>.  
  
 Сведения о синтаксисе и примеры см. в описании свойств <xref:System.Windows.Data.Binding.Path%2A> и <xref:System.Windows.Data.Binding.XPath%2A>.  
  
 Обратите внимание, что хотя мы и подчеркнули, что путь <xref:System.Windows.Data.Binding.Path%2A> к используемому значению является одним из четырех необходимых компонентов связывания, в скриптах, которые требуется привязать к всему объекту, используемое значение должно быть таким же, как и у объекта [источника привязки](GTMT).  В этих случаях оно применяется без указания <xref:System.Windows.Data.Binding.Path%2A>.  Рассмотрим следующий пример:  
  
 [!code-xml[MasterDetail#EmptyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 В приведенном выше примере используется синтаксис пустой привязки: {Привязка}.  В этом случае <xref:System.Windows.Controls.ListBox> наследует DataContext от родительского элемента DockPanel \(не показан в этом примере\).  Если путь не указан, по умолчанию производится привязка к всему объекту.  Другими словами, в этом примере путь не был указан, так как мы выполнили привязку свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> ко всему объекту.  \(Подробное обсуждение см. в разделе [Привязка к коллекции](#binding_to_collections).\)  
  
 Кроме привязки к коллекции, этот скрипт полезен также для возможности привязки ко всему объекту, а не только к одному свойству объекта.  Например, если объект источника является объектом строкового типа, и всего лишь нужна привязка к самой строке.  Другим распространенным скриптом является необходимость привязки элемента к объекту с несколькими свойствами.  
  
 Обратите внимание, что вам, возможно, потребуется применить пользовательскую логику, чтобы данные были применимы к вашему привязанному свойству цели.  Пользовательская логика может быть представлена в виде пользовательского преобразователя \(если не существует преобразования типа по умолчанию\).  Сведения о преобразователях см. в разделе [Преобразование данных](#data_conversion).  
  
<a name="binding_bindingexpression"></a>   
### Связывание и выражение привязки  
 До разъяснения других функций и использования привязки данных, было бы полезно рассказать о классе <xref:System.Windows.Data.BindingExpression>.  Как было показано в предыдущих разделах, класс <xref:System.Windows.Data.Binding> является классом высокого уровня для объявления привязки; класс <xref:System.Windows.Data.Binding> предоставляет множество свойств, которые позволяют указать характеристики привязки.  Связанный класс, <xref:System.Windows.Data.BindingExpression>, является базовым объектом, поддерживающим связь между источником и целью.  Привязка содержит всю информацию, которая может использоваться совместно в нескольких выражениях привязки.  <xref:System.Windows.Data.BindingExpression> представляет собой экземпляр выражения, который не может быть общим и который содержит все сведения об экземпляре <xref:System.Windows.Data.Binding>.  
  
 Например, рассмотрим следующую ситуацию, когда *myDataObject* является экземпляром класса*MyData*, *myBinding* является источником объекта <xref:System.Windows.Data.Binding>, а класс*MyData* представляет собой определенный класс, содержащий строковое свойство *MyDataProperty*.  В этом примере привязывается текстовое содержимое *MyText*, экземпляр класса <xref:System.Windows.Controls.TextBlock>, к *MyDataProperty*.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Можно использовать один и тот же объект *myBinding* для создания других привязок.  Например, можно использовать объект *myBinding* для привязки текстового содержимого элемента флажка к *MyDataProperty*.  В этом сценарии будут два экземпляра <xref:System.Windows.Data.BindingExpression>, совместно использующих объект *myBinding*.  
  
 Объект <xref:System.Windows.Data.BindingExpression> может быть получен с помощью возвращаемого значения метода <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> для объекта с привязкой к данным.  В следующих разделах демонстрируются некоторые примеры использования класса <xref:System.Windows.Data.BindingExpression>:  
  
-   [Получение объекта привязки из свойства целевого объекта привязки](../../../../docs/framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
-   [Управление обновлением источника из поля TextBox](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## Преобразование данных  
 В предыдущем примере кнопка красная, так как ее свойство <xref:System.Windows.Controls.Control.Background%2A> привязано к строковому свойству со значением "Красный".  Это работает, поскольку для типа <xref:System.Windows.Media.Brush> существует преобразователь, который преобразует строковое значение в значение типа <xref:System.Windows.Media.Brush>.  
  
 Если добавить эти сведения в рисунок из раздела [Создание привязки](#creating_a_binding), то диаграмма будет выглядеть следующим образом:  
  
 ![Схема привязки данных](../../../../docs/framework/wpf/data/media/databindingbuttondefaultconversion.png "DataBindingButtonDefaultConversion")  
  
 Однако, что делать, если вместо свойства строкового типа объект источника привязки имеет свойство *Цвет* типа <xref:System.Windows.Media.Color>?  В этом случае для создания привязки в первую очередь необходимо преобразовать значение свойства *Цвет* во что\-то, что примет свойство <xref:System.Windows.Controls.Control.Background%2A>.  Необходимо создать пользовательский преобразователь, реализующий интерфейс <xref:System.Windows.Data.IValueConverter>, как в следующем примере:  
  
 [!code-csharp[ColorPicker_snip#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 Страница ссылки <xref:System.Windows.Data.IValueConverter> предоставляет дополнительные сведения.  
  
 Теперь пользовательский преобразователь используется вместо преобразования по умолчанию, и наша диаграмма выглядит следующим образом:  
  
 ![Схема привязки данных](../../../../docs/framework/wpf/data/media/databindingconvertercolorexample.png "DataBindingConverterColorExample")  
  
 Таким образом, преобразования по умолчанию могут быть доступны благодаря преобразователям типов, присутствующим в типе, к которому производится привязка.  Такое поведение будет зависеть от того, какие преобразователи типов доступны в цели.  Если существуют какие\-то сомнением, создайте свой собственный преобразователь.  
  
 Ниже приведены некоторые типовые сценарии, где имеет смысл реализация преобразователя данных.  
  
-   Данные должны отображаться по\-разному, в зависимости от региональных стандартов.  Например, можно реализовать преобразователь валюты или преобразователь даты\/времени в календаре на основе значений или стандартов, используемых в определенных региональных стандартах.  
  
-   Используемые данные не обязательно предназначены для изменения текстового значения свойства, а предназначены для изменения некоторых других значений, например, источника изображения, цвета или стиля отображаемого текста.  Преобразователи могут использоваться в данном экземпляре для преобразования привязки неподходящего свойства, например, привязки текстового поля к свойству Background ячейки таблицы.  
  
-   К одним и тем же данным может быть привязано более одного элемента управления или несколько свойств элемента управления.  В этом случае основная привязка может просто отображать текст, тогда как другие привязки обрабатывают специфичные проблемы отображения, но они по\-прежнему используют одну и ту же привязку в качестве источника информации.  
  
-   Пока еще мы не рассматривали <xref:System.Windows.Data.MultiBinding>, где свойство цели имеет коллекцию привязок.  В случае <xref:System.Windows.Data.MultiBinding> следует использовать пользовательский <xref:System.Windows.Data.IMultiValueConverter> для получения окончательного значения из значений привязок.  Например, цвет может быть вычислен из соотношения красного, синего и зеленого значений, которые могут быть значениями одних и тех же или разных объектов источника привязки.  Примеры и другие сведения содержатся на странице класса <xref:System.Windows.Data.MultiBinding>.  
  
<a name="binding_to_collections"></a>   
## Привязка к коллекциям  
   
  
 Объект источника привязки может рассматриваться как отдельный объект, свойства которого содержат данные, или как коллекцию данных полиморфных объектов, часто группируемых вместе \(например, в результате запроса к базе данных\).  Пока еще мы обсуждали привязку только к одному объекту, однако привязка к коллекции данных является распространенным скриптом.  Распространенным сценарием является использование элементов управления <xref:System.Windows.Controls.ItemsControl>, таких как <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>, или <xref:System.Windows.Controls.TreeView>, для отображения коллекции данных, как, например, в приложении, показанном в разделе [Понятие о привязке данных](#what_is_data_binding).  
  
 К счастью, наша основная диаграмма по\-прежнему применима.  Если привязать <xref:System.Windows.Controls.ItemsControl> к коллекции, диаграмма будет выглядеть следующим образом:  
  
 ![Схема ItemsControl привязки данных](../../../../docs/framework/wpf/data/media/databindingitemscontrol.png "DataBindingItemsControl")  
  
 Как показано на этой диаграмме, выполнить привязку <xref:System.Windows.Controls.ItemsControl> к объекту коллекции можно с помощью свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>.  Свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> можно представить как содержимое <xref:System.Windows.Controls.ItemsControl>.  Обратите внимание, что привязка является привязкой типа <xref:System.Windows.Data.BindingMode>, поскольку свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> по умолчанию поддерживает привязку <xref:System.Windows.Data.BindingMode>.  
  
<a name="how_to_implement_collections"></a>   
### Способы реализации коллекций  
 Пользователь может выполнить перечисление элементов любой коллекции, реализующей интерфейс <xref:System.Collections.IEnumerable>.  Однако чтобы настроить динамические привязки таким образом, чтобы вставки и удаления элементов в коллекции автоматически обновляли [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], в коллекции должен быть реализован интерфейс <xref:System.Collections.Specialized.INotifyCollectionChanged>.  Этот интерфейс предоставляет событие, которое должно быть инициировано при изменении базовой коллекции.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет класс <xref:System.Collections.ObjectModel.ObservableCollection%601>, который является встроенной реализацией коллекции данных, предоставляющей интерфейс <xref:System.Collections.Specialized.INotifyCollectionChanged>.  Обратите внимание, что для полной поддержки передачи значений данных от объектов источника в цели каждый объект в коллекции, который поддерживает свойства связывания, должен также реализовывать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>.  Дополнительные сведения см. в разделе [Общие сведения об источниках привязки](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 До реализации собственной коллекции рассмотрите возможность использования класса <xref:System.Collections.ObjectModel.ObservableCollection%601> или одного из существующих классов коллекций, таких как <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> и <xref:System.ComponentModel.BindingList%601> \(среди многих прочих\).  Если имеется расширенный скрипт и требуется реализовать свою собственную коллекцию, следует рассмотреть возможность использования <xref:System.Collections.IList>, которая предоставляет коллекцию объектов, к которым можно по отдельности обращаться по индексу и следовательно, максимально быстро.  
  
<a name="collection_views"></a>   
### Представления коллекций  
 Так как <xref:System.Windows.Controls.ItemsControl> связан с коллекцией данных, существует возможность сортировать, фильтровать или группировать данные.  Для этого используется представления коллекций, которые являются классами, реализующими интерфейс <xref:System.ComponentModel.ICollectionView>.  
  
   
  
<a name="what_are_collection_views"></a>   
#### Понятие о представлениях коллекций  
 Представление коллекции — это слой, расположенный в верхней части связанной исходной коллекции, с помощью которого можно перемещаться по исходной коллекции и просматривать ее содержимое на основе запросов сортировки, фильтрации и группировки, не изменяя саму коллекцию.  В представлении коллекции также поддерживается указатель на текущий элемент коллекции.  Если в исходной коллекции реализован интерфейс <xref:System.Collections.Specialized.INotifyCollectionChanged>, изменения, инициированные событием <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>, передаются представлениям.  
  
 Поскольку представления не изменяют базовые исходные коллекции, каждая исходная коллекция может иметь несколько связанных с ней представлений.  Например, можно иметь коллекцию объектов *Задача*.  С помощью представлений можно отображать одни и те же данные различными способами.  Например, в левой части страницы можно отображать задачи, отсортированные по приоритету, а справа — сгруппированные по областям.  
  
<a name="how_to_create_a_view"></a>   
#### Создание представления  
 Одним из способов создания и использования представления является непосредственное создание объекта представления, и затем использование его в качестве источника привязки.  В качестве примера рассмотрим приложение, представленное в документе [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703), которое показано в разделе [Понятие о привязке к данным](#what_is_data_binding).  Приложение реализовано таким образом, что <xref:System.Windows.Controls.ListBox> привязывается к представлению коллекции данных, а не к коллекции данных напрямую.  Следующий пример извлечен из приложения [Пример привязки данных](http://go.microsoft.com/fwlink/?LinkID=163703).  Класс <xref:System.Windows.Data.CollectionViewSource> является прокси [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для класса, производного от <xref:System.Windows.Data.CollectionView>.  В этом отдельном примере источник <xref:System.Windows.Data.CollectionViewSource.Source%2A> представления привязан к коллекции *AuctionItems* \(типа <xref:System.Collections.ObjectModel.ObservableCollection%601>\) объекта текущего приложения.  
  
 [!code-xml[DataBindingLab#WindowResources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xml[DataBindingLab#CollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xml[DataBindingLab#WindowResources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 Ресурс *listingDataView* затем служит источником привязки для элементов в приложении, таких как <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Чтобы создать другое представление для той же коллекции, можно создать другой экземпляр <xref:System.Windows.Data.CollectionViewSource> и присвоить ему другое имя `x:Key`.  
  
 В приведенной ниже таблице показано, какие типы данных представления созданы в качестве представления коллекции по умолчанию либо объектом <xref:System.Windows.Data.CollectionViewSource> на основе типа исходной коллекции.  
  
|Тип исходной коллекции|Тип представления коллекции|Примечания|  
|----------------------------|---------------------------------|----------------|  
|<xref:System.Collections.IEnumerable>|Внутренний тип, основанный на <xref:System.Windows.Data.CollectionView>|Не удается сгруппировать элементы.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Самый быстрый.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### Использование представления по умолчанию  
 Один из способов создания и использования представления коллекции заключается в указании представления коллекции в качестве источника привязки.  WPF также создает представление коллекции по умолчанию для каждой коллекции, используемой в качестве источника привязки.  Если выполнить привязку непосредственно к коллекции, WPF выполнит привязку к представлению коллекции по умолчанию.  Обратите внимание, что данное представление по умолчанию совместно используется всеми привязками к одной и той же коллекции, поэтому изменения, внесенные в представление по умолчанию одним привязанным элементом управления либо кодом \(например сортировка или изменение указателя на текущий элемент, что будет рассмотрено ниже\), распространяются на все привязки к одной коллекции.  
  
 Чтобы получить представление по умолчанию, используйте метод <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A>.  Пример см. в разделе [Получение представления по умолчанию для коллекции данных](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  
  
##### Использование представлений коллекций с таблицами данных ADO.NET  
 Для повышения производительности представления коллекций для объектов ADO.NET <xref:System.Data.DataTable> и <xref:System.Data.DataView> делегируют функции сортировки и фильтрации объекту <xref:System.Data.DataView>.  При этом функции сортировки и фильтрации совместно используются всеми представлениями коллекции для источника данных.  Чтобы включить возможность независимой сортировки и фильтрации для каждого представления коллекции, инициализируйте каждое представление коллекции с использованием собственного объекта <xref:System.Data.DataView>.  
  
<a name="sorting"></a>   
#### Сортировка  
 Как уже отмечалось ранее, представления могут применять сортировку для коллекции.  Так как данные находятся в базовой коллекции, они могут иметь или не иметь некий порядок следования.  Представление коллекции позволяет установить порядок или изменить порядок, используемый по умолчанию, на основе введенных признаков сравнения.  Так как это представление данных на стороне клиента, распространенным скриптом является сортировка пользователем столбцов табличных данных по значениям, содержащимся в столбце.  С использованием представлений, управляемая пользователем сортировка может применяться еще раз без необходимости внесения изменений в основную коллекцию или создания повторного запроса к содержимому коллекции.  Пример см. в разделе [Сортировка столбцов GridView при нажатии на заголовок](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 В следующем примере показана логика сортировки для флажка <xref:System.Windows.Controls.CheckBox> "Сортировать по категории и дате" в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения, описанного в разделе [Понятие о привязке к данным](#what_is_data_binding).  
  
 [!code-csharp[DataBindingLab#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
<a name="filtering"></a>   
#### Фильтрация  
 Представления могут применять к коллекции фильтр.  Это означает, что несмотря на то, что элемент может существовать в коллекции, его конкретное представление предназначено для отображения только некоторого подмножества полной коллекции.  Возможна фильтрация по условию в данных.  Например, как показано в приложении из раздела [Понятие о привязке к данным](#what_is_data_binding), флажок <xref:System.Windows.Controls.CheckBox> "Показывать только товары по сниженным ценам" содержит логику фильтрации товаров с ценой 25 долл. США и выше.  Следующий код выполняется для установки фильтра *ShowOnlyBargainsFilter* в качестве обработчика событий <xref:System.Windows.Data.CollectionViewSource.Filter> при выборе этого <xref:System.Windows.Controls.CheckBox>:  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Обработчик событий *ShowOnlyBargainsFilter* реализуется следующим образом:  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Если используется один из классов <xref:System.Windows.Data.CollectionView> непосредственно вместо <xref:System.Windows.Data.CollectionViewSource>, следует использовать свойство <xref:System.Windows.Data.CollectionView.Filter%2A> для указания обратного вызова.  Пример см. в разделе [Фильтрация данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).  
  
<a name="grouping"></a>   
#### Группировка  
 За исключением внутреннего класса, предназначенного для просмотра коллекции <xref:System.Collections.IEnumerable>, все представления коллекций поддерживают функцию группировки, которая позволяет пользователю логически разбить коллекцию в представлении коллекции на группы.  Группы могут быть явными, если пользователь предоставляет список групп, или неявными, если эти группы создаются динамически в зависимости от данных.  
  
 В следующем примере показана логика флажка <xref:System.Windows.Controls.CheckBox> "Группировка по категориям"  
  
 [!code-csharp[DataBindingLab#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 Другой пример группировки см. в разделе [Группировка элементов в объекте ListView, реализующем GridView](../../../../docs/framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).  
  
<a name="current_record_pointers"></a>   
#### Указатели на текущий элемент  
 В представлениях также присутствует понятие текущего элемента.  Существует возможность перемещаться по объектам в представлении коллекции.  При переходе перемещается указатель элемента, позволяющий извлечь объект, расположенный в определенном месте в коллекции.  Пример см. в разделе [Перемещение по объектам в Data CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
 Поскольку WPF выполняет привязку к коллекции только через представление коллекции \(либо указанное пользователем, либо представление коллекции по умолчанию\), для всех привязок к коллекциям имеется указатель на текущий элемент.  При привязке к представлению знак косой черты \("\/"\) в значении `Path` указывает на текущий элемент представления.  В приведенном ниже примере контекст данных является представлением коллекции.  В первой строке выполняется привязка к коллекции.  Во второй строке выполняется привязка к текущему элементу коллекции.  В третьей строке выполняется привязка к свойству `Description` текущего элемента коллекции.  
  
```xaml  
<Button Content="{Binding }" />  
<Button Content="{Binding Path=/}" />  
<Button Content="{Binding Path=/Description}" />   
```  
  
 Косую черту и синтаксис свойства также можно комбинировать для обработки иерархии коллекций.  В приведенном ниже примере выполняется привязка к текущему элементу коллекции `Offices`, которая является свойством текущего элемента исходной коллекции.  
  
```xaml  
<Button Content="{Binding /Offices/}" />  
```  
  
 На указатель текущего элемента влияют примененные к коллекции операции сортировки и фильтрации.  При сортировке указатель текущего элемента устанавливается на последний выбранный элемент, однако представление коллекции перестраивается относительно его.  \(Возможно, до этого выбранный элемент был в начале списка, но теперь выбранный элемент может оказаться где\-нибудь в середине\). При фильтрации выбранный элемент сохраняется, если данный выбор остается в представлении после фильтрации.  В противном случае указатель текущего элемента устанавливается на первый элемент отфильтрованного представления коллекции.  
  
<a name="master_detail_scenario"></a>   
#### Скрипт привязки "основной\/подробности"  
 Понятие текущего элемента применимо не только для перемещения элементов в коллекции, но также для скрипта привязки "основной\/подробности".  Еще раз рассмотрим [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения из раздела[Понятие о привязке к данным](#what_is_data_binding).  В этом приложении выделение в <xref:System.Windows.Controls.ListBox> определяет содержимое, показанное в <xref:System.Windows.Controls.ContentControl>.  При выборе элемента <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ContentControl> отображает подробные сведения о выбранном элементе, что позволяет поместить выделение другим способом.  
  
 Для выполнения скрипта необходимо наличие двух или более элементов управления, привязанных к одному и тому же представлению.  В следующем примере из документа [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703) показывается разметка элементов управления <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ContentControl>, которые можно видеть в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения из раздела [Понятие о привязке к данным](#what_is_data_binding).  
  
 [!code-xml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xml[DataBindingLab#Detail](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Обратите внимание, что оба элемента управления привязаны к одному источнику, статическому ресурсу *listingDataView* \(просмотреть определение этого ресурса можно в разделе [Создание представления](#how_to_create_a_view)\).  Это работает, так как если объект одноэлементного множества \(в данном случае <xref:System.Windows.Controls.ContentControl>\) связан с представлением коллекции, он автоматически привязывается к <xref:System.Windows.Data.CollectionView.CurrentItem%2A> представления.  Обратите внимание, что объекты <xref:System.Windows.Data.CollectionViewSource> автоматически синхронизуют значения денежного формата и выделение.  Если элемент управления списка не привязан к объекту <xref:System.Windows.Data.CollectionViewSource>, как в этом примере, для корректной работы необходимо задать его свойству <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> значение `true`.  
  
 Другие примеры содержатся в разделах [Привязка к коллекции и вывод сведений в зависимости от выделенного элемента](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) и [Использование шаблона "главный\-подчиненный" с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Можно заметить, что в приведенном выше примере используется шаблон.  Фактически данные не будут отображаться выбранным способом без использования шаблонов \(один явно используется элементом <xref:System.Windows.Controls.ContentControl>, а другой — неявно элементом <xref:System.Windows.Controls.ListBox>\).  К шаблонам данных мы перейдем в следующем разделе.  
  
<a name="data_templating"></a>   
## Шаблоны данных  
 Без использования шаблонов данных [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения из раздела [Понятие о привязке к данным](#what_is_data_binding) будет выглядеть следующим образом:  
  
 ![Демонстрация привязки данных без шаблонов данных](../../../../docs/framework/wpf/data/media/databindingdemotemplates.png "DataBindingDemoTemplates")  
  
 Как показано в примере из предыдущего раздела, оба элемента управления <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ContentControl> привязываются ко всему объекту коллекции \(а точнее, к представлению объекта коллекции\) элементов *AuctionItem*.  При отсутствии особых инструкций по способу отображения сбора данных элемент управления <xref:System.Windows.Controls.ListBox> отображает строковое представление каждого объекта в базовой коллекции, а элемент управления <xref:System.Windows.Controls.ContentControl> отображает строковое представление привязанного к ней объекта.  
  
 Чтобы устранить эту проблему, приложение задает шаблоны <xref:System.Windows.DataTemplate>.  Как показано в примере из предыдущего раздела, элемент управления <xref:System.Windows.Controls.ContentControl> явно использует шаблон *detailsProductListingTemplate* <xref:System.Windows.DataTemplate>.  Элемент управления <xref:System.Windows.Controls.ListBox> неявно использует следующий <xref:System.Windows.DataTemplate> для отображении объектов *AuctionItem* в коллекции:  
  
 [!code-xml[DataBindingLab#AuctionItemDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 При использовании двух шаблонов <xref:System.Windows.DataTemplate> результирующий пользовательский интерфейс будет аналогичен пользовательскому интерфейсу, показанному в разделе [Понятие о привязке к данным](#what_is_data_binding).  Как можно увидеть из этого снимка, в дополнение к тому, что шаблоны <xref:System.Windows.DataTemplate> дают возможность располагать данные в элементах управления, они позволяют определять подходящие визуальные элементы для данных.  Например, элементы <xref:System.Windows.DataTrigger> используются в указанном выше <xref:System.Windows.DataTemplate>, так что элементы*AuctionItem* со значением *SpecialFeatures* для *HighLight* будут отображаться с оранжевой границей и звездочкой.  
  
 Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="data_validation"></a>   
## Проверка данных  
   
  
 Для большинства приложений, принимающих входные данные от пользователя, необходима логика проверки, чтобы убедиться, что пользователь ввел ожидаемые данные.  Проверка может основываться на типе, диапазоне, формате или других требованиях конкретного приложения.  В этом разделе рассматривается, как проверка данных работает в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="validation_rules"></a>   
### Связь проверочных правил и привязки  
 Модель привязки данных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет связать свойство <xref:System.Windows.Data.Binding.ValidationRules%2A> с объектом <xref:System.Windows.Data.Binding>.  Например, в следующем примере выполняется привязка элемента управления <xref:System.Windows.Controls.TextBox> к свойству с именем `StartPrice` и добавление объекта <xref:System.Windows.Controls.ExceptionValidationRule> к свойству <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=fullName>.  
  
 [!code-xml[DataBindingLab#DefaultValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 Объект <xref:System.Windows.Controls.ValidationRule> выполняет проверку допустимости значения свойства.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется два следующих типа встроенных объектов <xref:System.Windows.Controls.ValidationRule>:  
  
-   Объект <xref:System.Windows.Controls.ExceptionValidationRule> проверяет исключения, возникшие во время обновления привязанного исходного свойства.  В предыдущем примере `StartPrice` имеет тип integer.  Когда пользователь вводит значение, которое невозможно преобразовать в целое число, создается исключение, приводящее к тому, что привязка будет помечена как недопустимая.  Чтобы явно установить <xref:System.Windows.Controls.ExceptionValidationRule>, можно также задать для свойства <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> значение `true` в объекте <xref:System.Windows.Data.Binding> или <xref:System.Windows.Data.MultiBinding>.  
  
-   Объект <xref:System.Windows.Controls.DataErrorValidationRule> выполняет проверку ошибок объектов, реализующих интерфейс <xref:System.ComponentModel.IDataErrorInfo>.  Пример использования этого правила проверки см. в разделе <xref:System.Windows.Controls.DataErrorValidationRule>.  Чтобы явно установить <xref:System.Windows.Controls.DataErrorValidationRule>, можно также задать для свойства <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> значение `true` в объекте <xref:System.Windows.Data.Binding> или <xref:System.Windows.Data.MultiBinding>.  
  
 Можно также создать свои собственные правила проверки, определив класс, производный от класса <xref:System.Windows.Controls.ValidationRule>, и реализовав метод <xref:System.Windows.Controls.ValidationRule.Validate%2A>.  В следующем примере показано правило, используемое элементом управления <xref:System.Windows.Controls.TextBox> "Дата начала" из окна *добавления продуктов*, показанного в разделе [Понятие о привязке к данным](#what_is_data_binding).  
  
 [!code-csharp[DataBindingLab#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> использует это правило *FutureDateRule*, как показано в следующем примере:  
  
 [!code-xml[DataBindingLab#CustomValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Обратите внимание, что поскольку значение <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> является <xref:System.Windows.Data.UpdateSourceTrigger>, механизм привязки обновляет значение источника при каждом нажатии клавиши, то есть он также проверяет каждое правило в коллекции <xref:System.Windows.Data.Binding.ValidationRules%2A> при каждом нажатии клавиши.  Это будет обсуждаться далее в разделе "Процесс проверки".  
  
<a name="invalidation_feedback"></a>   
### Предоставление визуального отклика  
 Если пользователь вводит недопустимое значение, следует обеспечить некоторый отклик приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] на ошибку.  Одним из способов обеспечения такого отклика является установка вложенного свойства <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=fullName> в пользовательский шаблон <xref:System.Windows.Controls.ControlTemplate>.  Как показано в предыдущем подразделе, *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> использует <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>, называемый *шаблоном проверки*.  В следующем примере рассмотрено определение элемента *Шаблон проверки*:  
  
 [!code-xml[DataBindingLab#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 Элемент <xref:System.Windows.Controls.AdornedElementPlaceholder> указывает, куда будет помещен выбранный элемент управления.  
  
 Кроме того, для вывода сообщения об ошибке можно использовать <xref:System.Windows.Controls.ToolTip>.  И *StartDateEntryForm*, и *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> используют стиль *textStyleTextBox*, который создает <xref:System.Windows.Controls.ToolTip>, отображающий сообщение об ошибке.  В следующем примере рассмотрено определение элемента *textStyleTextBox*:  [Вложенное свойство](GTMT) <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> принимает значение `true`, если одна или несколько привязок к свойствам связанного элемента вызвали ошибку.  
  
 [!code-xml[DataBindingLab#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 При использовании пользовательских шаблонов <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> и <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.TextBox> форма *StartDateEntryForm* при ошибке проверки выглядит следующим образом:  
  
 ![Ошибка проверки привязки данных](../../../../docs/framework/wpf/data/media/databindingdemo-validation.png "DataBindingDemo\_Validation")  
  
 Если привязка <xref:System.Windows.Data.Binding> имеет правила проверки, но не указан <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> на присоединенном элементе управления, для уведомления пользователей об ошибке проверки по умолчанию будет использоваться <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>.  <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> по умолчанию — это шаблон элемента управления, определяющий красную границу графического уровня.  С используемым по умолчанию <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> и с <xref:System.Windows.Controls.ToolTip>, элемент [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] формы *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> при ошибке проверки выглядит следующим образом:  
  
 ![Ошибка проверки привязки данных](../../../../docs/framework/wpf/data/media/databindingdemo-validationdefault.png "DataBindingDemo\_ValidationDefault")  
  
 Пример обеспечения логики проверки всех элементов управления в диалоговом окне содержится в разделе "Пользовательские диалоговые окна" в [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
<a name="validation_process"></a>   
### Процесс проверки  
 Проверка обычно выполняется, когда целевое значение передается свойству источника привязки.  Это выполняется для типов привязки <xref:System.Windows.Data.BindingMode> и <xref:System.Windows.Data.BindingMode>.  Таким образом, причина обновления источника зависит от значения свойства <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>, как описано в разделе [Что инициирует обновления источника](#what_triggers_source_updates).  
  
 Ниже описан процесс *проверки*.  Обратите внимание, что при возникновении ошибки проверки или ошибки другого типа на любом этапе данного процесса процесс будет прерван.  
  
1.  Обработчик привязки проверяет наличие настраиваемых объектов <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которых присвоено значение <xref:System.Windows.Controls.ValidationStep> для данного типа привязки <xref:System.Windows.Data.Binding>; в этом случае для каждого правила <xref:System.Windows.Controls.ValidationRule> вызывается метод <xref:System.Windows.Controls.ValidationRule.Validate%2A>, пока одно из них не вернет ошибку или пока все они не будут выполнены.  
  
2.  Обработчик привязки вызывает преобразователь, если таковой существует.  
  
3.  При успешном завершении работы преобразователя обработчик привязки проверяет наличие настраиваемых объектов <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которых присвоено значение <xref:System.Windows.Controls.ValidationStep> для данного типа привязки <xref:System.Windows.Data.Binding>; в этом случае для каждого правила <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которого присвоено значение <xref:System.Windows.Controls.ValidationStep>, вызывается метод <xref:System.Windows.Controls.ValidationRule.Validate%2A>, пока одно из них не вернет ошибку или пока все они не будут выполнены.  
  
4.  Обработчик привязки присваивает значение исходному свойству.  
  
5.  Обработчик привязки проверяет наличие настраиваемых объектов <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которых присвоено значение <xref:System.Windows.Controls.ValidationStep> для данного типа привязки <xref:System.Windows.Data.Binding>; в этом случае для каждого правила <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которого присвоено значение <xref:System.Windows.Controls.ValidationStep>, вызывается метод <xref:System.Windows.Controls.ValidationRule.Validate%2A>, пока одно из них не вернет ошибку или пока все они не будут выполнены.  Если правило <xref:System.Windows.Controls.DataErrorValidationRule> связано с привязкой и его свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> задано значение по умолчанию, <xref:System.Windows.Controls.ValidationStep>, в этой точке производится проверка правила <xref:System.Windows.Controls.DataErrorValidationRule>.  В этой же точке проверяются привязки, в которых для свойства <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> установлено значение `true`.  
  
6.  Обработчик привязки проверяет наличие настраиваемых объектов <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которых присвоено значение <xref:System.Windows.Controls.ValidationStep> для данного типа привязки <xref:System.Windows.Data.Binding>; в этом случае для каждого правила <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которого присвоено значение <xref:System.Windows.Controls.ValidationStep>, вызывается метод <xref:System.Windows.Controls.ValidationRule.Validate%2A>, пока одно из них не вернет ошибку или пока все они не будут выполнены.  
  
 Если правило <xref:System.Windows.Controls.ValidationRule> не выполняется на любом этапе данного процесса, обработчик привязки создает объект <xref:System.Windows.Controls.ValidationError> и добавляет его в коллекцию <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> связанного элемента.  Перед запуском обработчиком привязки объектов <xref:System.Windows.Controls.ValidationRule> на любом этапе обработчик привязки удаляет все объекты <xref:System.Windows.Controls.ValidationError>, добавленные во <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> [вложенное свойство](GTMT) связанного элемента на соответствующем этапе.  Например, если правило <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которого присвоено значение <xref:System.Windows.Controls.ValidationStep>, не выполняется, то при следующей проверке обработчик привязки удалит объект <xref:System.Windows.Controls.ValidationError> непосредственно перед вызовом любого правила <xref:System.Windows.Controls.ValidationRule>, свойству <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> которого присвоено значение <xref:System.Windows.Controls.ValidationStep>.  
  
 Если свойство <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> не пусто, <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> [вложенному свойству](GTMT) элемента присваивается значение `true`.  Кроме того, если свойству <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> объекта <xref:System.Windows.Data.Binding> присвоено значение `true`, обработчик привязки вызывает <xref:System.Windows.Controls.Validation.Error?displayProperty=fullName> [вложенное событие](GTMT) элемента.  
  
 Также обратите внимание, что при передаче допустимого значения в любом направлении \(от целевого объекта к источнику и от источника к целевому объекту\) очищается <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> [вложенное свойство](GTMT).  
  
 Если для привязки задано связанное с ней правило <xref:System.Windows.Controls.ExceptionValidationRule> или для ее свойства <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> задано значение `true` и при задании обработчиком привязки значения источника возникает исключение, обработчик привязки проверяет наличие фильтра <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>.  Имеется возможность использования отклика <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> для возможности создания пользовательского обработчика исключений.  Если фильтр исключений <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> для привязки <xref:System.Windows.Data.Binding> не указан, обработчик привязки создает объект <xref:System.Windows.Controls.ValidationError> с исключением и добавляет его в коллекцию <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> связанного элемента.  
  
<a name="debugging_mechanism"></a>   
## Механизм отладки  
 Можно установить вложенное свойство <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=fullName> связанного с привязкой объекта для получения сведений о состоянии конкретной привязки.  
  
## См. также  
 <xref:System.Windows.Controls.DataErrorValidationRule>   
 [Новые возможности WPF версии 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)   
 [Привязка к результатам запроса LINQ](../../../../docs/framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)   
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703)   
 [Практические руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Привязка к источнику данных ADO.NET](../../../../docs/framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)