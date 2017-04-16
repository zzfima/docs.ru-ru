---
title: "UI Automation and Microsoft Active Accessibility | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Active Accessibility"
  - "UI Automation, Active Accessibility compared to"
  - "UI Automation, Microsoft Active Accessibility"
  - "Active Accessibility, UI Automation compared to"
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
caps.latest.revision: 24
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 23
---
# UI Automation and Microsoft Active Accessibility
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Предыдущее решение по обеспечению доступности приложений — [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] — это новая модель специальных возможностей для [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)], предназначенная для удовлетворения потребностей продуктов поддержки специальных возможностей и средств автоматизированного тестирования.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет множество улучшений по сравнению с [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
 В этом разделе рассматриваются основные функции [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и объясняется, как эти функции отличаются от [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
<a name="Programming_Languages_compare"></a>   
## Языки программирования  
 Модель [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] построена на основе [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)] с поддержкой сдвоенных интерфейсов и поэтому доступна для программирования на C\/C\+\+, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)] и на скриптовых языках. Модель [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] \(включая библиотеку поставщика на стороне клиента для стандартных элементов управления\) написана в управляемом коде, и клиентские приложения модели автоматизации пользовательского интерфейса проще всего программировать на [!INCLUDE[TLA#tla_vcshrp](../../../includes/tlasharptla-vcshrp-md.md)] или [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]. Поставщики автоматизации пользовательского интерфейса, которые являются реализациями интерфейса, могут быть написаны в управляемом коде или на C\/C\+\+.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## Поддержка в Windows Presentation Foundation  
 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] — это новая модель создания пользовательских интерфейсов. В элементах [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] не предусмотрена собственная поддержка [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]; однако они поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], включая использование моста для клиентов [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Только клиенты, написанные специально для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], могут использовать все преимущества специальных возможностей [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], таких как расширенная поддержка текста.  
  
<a name="Servers_and_Clients_compare"></a>   
## Серверы и клиенты  
 В [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] серверы и клиенты взаимодействуют напрямую, по большей части через серверную реализацию `IAccessible`.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] основная служба находится между сервером \(называемым поставщиком\) и клиентом. Основная служба выполняет вызовы интерфейсов, реализованных поставщиками, и предоставляет дополнительные службы, такие как создание уникальных идентификаторов среды выполнения для элементов. Клиентские приложения используют функции библиотеки для вызова службы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 Поставщики автоматизации пользовательского интерфейса могут предоставлять сведения клиентам [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], а серверы [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] — предоставлять сведения клиентским приложениям модели автоматизации пользовательского интерфейса. Однако поскольку [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] предоставляет меньше сведений, чем [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], эти две модели не являются полностью совместимыми.  
  
<a name="UI_Elements_compare"></a>   
## Элементы пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] представляет элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] либо в виде интерфейса `IAccessible`, либо в виде идентификатора дочернего элемента. Трудно сравнивать два указателя `IAccessible`, чтобы определить, ссылаются ли они на один и тот же элемент.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] каждый элемент представлен как объект <xref:System.Windows.Automation.AutomationElement>. Сравнение выполняется с помощью оператора равенства или метода <xref:System.Windows.Automation.AutomationElement.Equals%2A>; в обоих способах сравниваются уникальные идентификаторы среды выполнения элементов.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## Представления в виде дерева и навигация  
 Элементы [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] на экране можно рассматривать как древовидную структуру с рабочим столом в качестве корня, окнами приложений в качестве непосредственных дочерних элементов и элементов в приложениях в качестве следующих потомков.  
  
 В [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] многие элементы автоматизации, которые не касаются конечных пользователей, представлены в дереве. Клиентские приложения должны просмотреть все элементы, чтобы определить имеющие значение.  
  
 Клиентские приложения модели автоматизации пользовательского интерфейса видят [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] через отфильтрованное представление. Это представление содержит только элементы, представляющие интерес, т. е. те, которые предоставляют пользователю сведения или разрешают взаимодействие. Доступны предопределенные представления только элементов управления и только элементов содержимого; кроме того, приложения могут задавать специальные представления.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] упрощает задачу описания [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] для пользователя и помогает пользователю взаимодействовать с приложением.  
  
 Навигация по элементам в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] может быть пространственной \(например, переход к элементу, который располагается слева на экране\), логической \(например, перемещение к следующему пункту меню или к следующему элементу в последовательности табуляции в диалоговом окне\) или иерархической \(например, перемещение в первый дочерний элемент в контейнере или от дочернего элемента к родительскому\). Иерархическая навигация осложняется тем, что дочерние элементы не всегда являются объектами, которые реализуют `IAccessible`.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] все элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] являются объектами <xref:System.Windows.Automation.AutomationElement>, которые поддерживают те же базовые функциональные возможности. \(С точки зрения поставщика они являются объектами, которые реализуют интерфейс, унаследованный от <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>.\) Большей частью навигация является иерархической: от родительских элементов к дочерним и от одного элемента того же уровня к следующему. \(Навигация между одноуровневыми элементами имеет логическую составляющую, так как она может следовать последовательности табуляции.\) Вы можете переходить из любой начальной точки, используя любое отфильтрованное представление дерева, с помощью класса <xref:System.Windows.Automation.TreeWalker>. Вы также можете переходить к конкретному дочернему элементу или к потомкам с помощью методов <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> и <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; например, очень легко получить все элементы в диалоговом окне, поддерживающем указанный шаблон элемента управления.  
  
 Навигация в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] более последовательна, чем в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Некоторые элементы, например раскрывающиеся списки и всплывающие окна, появляются дважды в дереве [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], и навигация из них может иметь непредсказуемые результаты. Фактически невозможно правильно реализовать [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] для элемента управления "Главная панель".[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] допускает переподчинение и изменение расположения, так что элемент можно разместить в любом месте дерева, независимо от иерархии, обусловленной принадлежностью окон.  
  
<a name="Roles_and_Control_Types"></a>   
## Роли и типы элементов управления  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] использует свойство `accRole` \(`IAccessible::get_actRole`\) для получения описания роли элемента в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], например ROLE\_SYSTEM\_SLIDER или ROLE\_SYSTEM\_MENUITEM. Роль элемента — это основной ключ к его доступным функциональным возможностям. Взаимодействие с элементом управления достигается с помощью фиксированных методов, таких как `IAccessible::accSelect` и `IAccessible::accDoDefaultAction`. Взаимодействие между клиентским приложением и [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ограничено тем, что может быть сделано с помощью `IAccessible`.  
  
 Напротив, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] во многом отделяет тип элемента управления \(описываемый свойством <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>\) от его ожидаемой функциональности. Функциональность определяется шаблонами элементов управления, которые поддерживаются поставщиком через его реализацию специализированных интерфейсов. Шаблоны элементов управления можно объединить для описания полного набора функциональных возможностей, поддерживаемых конкретным элементом [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Некоторые поставщики обязаны поддерживать определенный шаблон элемента управления; например, поставщик флажка должен поддерживать шаблон элемента управления Toggle. Другие поставщики должны поддерживать хотя бы один набор шаблонов элементов управления; например, кнопки должны поддерживать Toggle или Invoke. Третьи поставщики вообще не поддерживают никакие шаблоны элементов управления; например, область, которую нельзя перемещать, изменять размер или закреплять, не имеет ни одного элемента управления.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] поддерживает пользовательские элементы управления, которые идентифицируются по свойству <xref:System.Windows.Automation.ControlType.Custom> и могут быть описаны свойством <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>.  
  
 В следующей таблице показано соответствие [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] ролей типам элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|Роль [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Тип элемента управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|----------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|  
|ROLE\_SYSTEM\_PUSHBUTTON|Кнопка|  
|ROLE\_SYSTEM\_CLIENT|Календарь|  
|ROLE\_SYSTEM\_CHECKBUTTON|Флажок|  
|ROLE\_SYSTEM\_COMBOBOX|Поле со списком|  
|ROLE\_SYSTEM\_CLIENT|Другой|  
|ROLE\_SYSTEM\_LIST|Сетка данных|  
|ROLE\_SYSTEM\_LISTITEM|Элемент данных|  
|ROLE\_SYSTEM\_DOCUMENT|Document|  
|ROLE\_SYSTEM\_TEXT|Правка|  
|ROLE\_SYSTEM\_GROUPING|Группа|  
|ROLE\_SYSTEM\_LIST|Header|  
|ROLE\_SYSTEM\_COLUMNHEADER|Элемент заголовка|  
|ROLE\_SYSTEM\_LINK|Гиперссылка|  
|ROLE\_SYSTEM\_GRAPHIC|Изображение|  
|ROLE\_SYSTEM\_LIST|Список|  
|ROLE\_SYSTEM\_LISTITEM|Элемент списка|  
|ROLE\_SYSTEM\_MENUPOPUP|Меню|  
|ROLE\_SYSTEM\_MENUBAR|Строка меню|  
|ROLE\_SYSTEM\_MENUITEM|Элемент меню|  
|ROLE\_SYSTEM\_PANE|Панель|  
|ROLE\_SYSTEM\_PROGRESSBAR|Индикатор выполнения|  
|ROLE\_SYSTEM\_RADIOBUTTON|Переключатель|  
|ROLE\_SYSTEM\_SCROLLBAR|Полоса прокрутки|  
|ROLE\_SYSTEM\_SEPARATOR|Separator|  
|ROLE\_SYSTEM\_SLIDER|Slider|  
|ROLE\_SYSTEM\_SPINBUTTON|Spinner|  
|ROLE\_SYSTEM\_SPLITBUTTON|Разворачивающаяся кнопка|  
|ROLE\_SYSTEM\_STATUSBAR|Строка состояния|  
|ROLE\_SYSTEM\_PAGETABLIST|Вкладка|  
|ROLE\_SYSTEM\_PAGETAB|Элемент вкладки|  
|ROLE\_SYSTEM\_TABLE|Таблица|  
|ROLE\_SYSTEM\_STATICTEXT|Text|  
|ROLE\_SYSTEM\_INDICATOR|Бегунок|  
|ROLE\_SYSTEM\_TITLEBAR|Заголовок окна|  
|ROLE\_SYSTEM\_TOOLBAR|Панель инструментов|  
|Tool barROLE\_SYSTEM\_TOOLTIP|ToolTip|  
|ROLE\_SYSTEM\_OUTLINE|Дерево|  
|ROLE\_SYSTEM\_OUTLINEITEM|Элемент дерева|  
|ROLE\_SYSTEM\_WINDOW|Окно|  
  
 Дополнительные сведения о разных типах элементов управления см. в разделе [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>   
## Состояния и свойства  
 В [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] элементы поддерживают общий набор свойств, и некоторые свойства \(например `accState`\) должны описывать очень разные вещи, в зависимости от роли элемента. Серверы должны реализовывать все методы `IAccessible`, возвращающие свойство, даже те, которые не относятся к элементу.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] определяет множество других свойств. Некоторые из них соответствует состояниям в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Одни свойства являются общими для всех элементов, а другие относятся к типам элементов управления и шаблонам элементов управления. Свойства различаются по уникальным идентификаторам, и большинство свойств можно получить с помощью одного метода, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> или <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Многие свойства легко извлекаются из методов доступа к свойствам <xref:System.Windows.Automation.AutomationElement.Current%2A> и <xref:System.Windows.Automation.AutomationElement.Cached%2A>.  
  
 Поставщик автоматизации пользовательского интерфейса не должен реализовывать ненужные свойства, он может просто возвращать значение `null` для всех свойств, которые он не поддерживает. Кроме того, основная служба [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] может получить некоторые свойства от поставщика окна по умолчанию, и эти свойства объединяются со свойствами, явно реализуемыми поставщиком.  
  
 Наряду с поддержкой множества дополнительных свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предлагает более высокую производительность, поскольку позволяет получать несколько свойств с помощью одного межпроцессного вызова.  
  
 В следующей таблице показано соответствие свойств в этих двух моделях.  
  
|Метод доступа к свойству [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Идентификатор свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Заметки|  
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> или <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|Если заданы оба свойства, `AccessKeyProperty` имеет более высокий приоритет.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>|``|  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Сопоставления ролей и типов элементов управления см. в предыдущей таблице.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName>|Допустимо только для типов элементов управления, которые поддерживают ValuePattern или RangeValuePattern. Значения RangeValue нормализованы в значения от 0 до 100 для согласованности с поведением MSAA. Элементы Value используют строку.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] не поддерживается.|`accDescription` не имеет четкой спецификации в MSAA, в результате чего поставщики помещают в это свойство разные части сведений.|  
|`get_accHelpTopic`|В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] не поддерживается.||  
  
 В следующей таблице показано, какие свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] соответствуют константам состояний [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
|Состояние [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Свойство [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Вызывает изменение состояния?|  
|---------------------------------------------------------------------------|------------------------------------------------------------------------------------|-----------------------------------|  
|STATE\_SYSTEM\_CHECKED|Для флажка — <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Для переключателя — <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Y|  
|STATE\_SYSTEM\_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState>|Y|  
|STATE\_SYSTEM\_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState> или <xref:System.Windows.Automation.ExpandCollapseState>|Y|  
|STATE\_SYSTEM\_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|в|  
|STATE\_SYSTEM\_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|в|  
|STATE\_SYSTEM\_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> для пунктов меню|в|  
|STATE\_SYSTEM\_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True и <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> вызывает <xref:System.Windows.Automation.NoClickablePointException>|в|  
|STATE\_SYSTEM\_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> \=<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|в|  
|STATE\_SYSTEM\_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> \= <xref:System.Windows.Automation.ToggleState>|в|  
|STATE\_SYSTEM\_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|в|  
|STATE\_SYSTEM\_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|в|  
|STATE\_SYSTEM\_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True|в|  
|STATE\_SYSTEM\_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|в|  
|STATE\_SYSTEM\_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=fullName> и <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=fullName>.|в|  
|STATE\_SYSTEM\_SELECTABLE|Поддерживается <xref:System.Windows.Automation.SelectionItemPattern>|в|  
|STATE\_SYSTEM\_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|в|  
|STATE\_SYSTEM\_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|в|  
|STATE\_SYSTEM\_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|Y|  
  
 Следующие состояния либо не реализованы большинством серверов управления [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], либо не имеют эквивалента в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|Состояние [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|Примечания|  
|---------------------------------------------------------------------------|----------------|  
|STATE\_SYSTEM\_BUSY|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_DEFAULT|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_ANIMATED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_EXTSELECTABLE|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_MARQUEED|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_SELFVOICING|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_TRAVERSED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_ALERT\_HIGH|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_ALERT\_MEDIUM|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_ALERT\_LOW|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_FLOATING|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE\_SYSTEM\_HOTTRACKED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_PRESSED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Полный список идентификаторов свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>   
## События  
 Механизм событий в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в отличие от [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], не полагается на маршрутизацию событий Windows \(которая тесно связана с дескрипторами окон\) и не требует, чтобы клиентское приложение устанавливало обработчики. Подписки на события можно детально настраивать не только для конкретных событий, но и для конкретных частей дерева. Поставщики также могут детально настраивать свой вызов событий, отслеживая, какие события прослушиваются.  
  
 Кроме того, клиентам стало проще получать элементы, которые вызывают события, поскольку они передаются напрямую в обратный вызов события. Свойства элемента автоматически предварительно выбираются, если запрос кэша был активен, когда клиент подписался на событие.  
  
 В следующей таблице показано соответствие событий WinEvent [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] и событий [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|WinEvent|Идентификатор события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|--------------|-------------------------------------------------------------------------------------------------|  
|EVENT\_OBJECT\_ACCELERATORCHANGE|Изменение свойства <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|  
|EVENT\_OBJECT\_CONTENTSCROLLED|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> или <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> в связанных полосах прокрутки|  
|EVENT\_OBJECT\_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_DEFACTIONCHANGE|Эквивалент отсутствует|  
|EVENT\_OBJECT\_DESCRIPTIONCHANGE|Нет точного эквивалента; возможно, изменение свойства <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> или <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT\_OBJECT\_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_OBJECT\_HELPCHANGE|Изменение <xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|  
|EVENT\_OBJECT\_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_LOCATIONCHANGE|Изменение свойства <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT\_OBJECT\_NAMECHANGE|Изменение свойства <xref:System.Windows.Automation.AutomationElement.NameProperty>|  
|EVENT\_OBJECT\_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_REORDER|Несогласованно используется в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Непосредственно соответствующее событие в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] не определено.|  
|EVENT\_OBJECT\_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT\_OBJECT\_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONWITHIN|Эквивалент отсутствует|  
|EVENT\_OBJECT\_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_STATECHANGE|Различные события изменения свойств|  
|EVENT\_OBJECT\_VALUECHANGE|Изменены <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName> и <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName>.|  
|EVENT\_SYSTEM\_ALERT|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_CAPTUREEND|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_CAPTURESTART|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_CONTEXTHELPEND|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_CONTEXTHELPSTART|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT\_SYSTEM\_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT\_SYSTEM\_DRAGDROPEND|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_DRAGDROPSTART|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_SYSTEM\_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MINIMIZEEND|Изменение свойства <xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT\_SYSTEM\_MINIMIZESTART|Изменение свойства <xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT\_SYSTEM\_MOVESIZEEND|Изменение свойства <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT\_SYSTEM\_MOVESIZESTART|Изменение свойства <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT\_SYSTEM\_SCROLLINGEND|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> или <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|EVENT\_SYSTEM\_SCROLLINGSTART|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> или <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|EVENT\_SYSTEM\_SOUND|Эквивалент отсутствует|  
|EVENT\_SYSTEM\_SWITCHEND|Нет эквивалента, но событие <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> сигнализирует, что новое приложение получило фокус|  
|EVENT\_SYSTEM\_SWITCHSTART|Эквивалент отсутствует|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty>|  
|Эквивалент отсутствует|Изменение свойства <xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|Эквивалент отсутствует|Событие <xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent>|  
|Эквивалент отсутствует|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## Безопасность  
 В некоторых сценариях настройки `IAccessible` требуется перенос базового `IAccessible` и вызов через него. Это влияет на безопасность, поскольку частично доверенный компонент не должен быть посредником на пути кода.  
  
 В модели [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] устранена необходимость вызова поставщиками кода другого поставщика. Основная служба [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] выполняет все необходимое агрегирование.  
  
## См. также  
 [UI Automation Fundamentals](../../../docs/framework/ui-automation/index.md)