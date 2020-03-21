---
title: Модель автоматизации пользовательского интерфейса и Microsoft Active Accessibility
ms.date: 03/30/2017
helpviewer_keywords:
- Active Accessibility
- UI Automation, Active Accessibility compared to
- UI Automation, Microsoft Active Accessibility
- Active Accessibility, UI Automation compared to
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
ms.openlocfilehash: 9a84c344ffabdaaa9d0aed68b05b7a4449776789
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179983"
---
# <a name="ui-automation-and-microsoft-active-accessibility"></a>Модель автоматизации пользовательского интерфейса и Microsoft Active Accessibility
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 Microsoft Active Accessibility была более ранним решением для обеспечения доступности приложений. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]является новой моделью доступности для Microsoft Windows и предназначена для удовлетворения потребностей вспомогательных технологических продуктов и автоматизированных инструментов тестирования. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]предлагает множество улучшений по сравнению с Active Accessibility.  
  
 Эта тема включает в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] себя основные особенности и объясняет, как эти функции отличаются от Active Accessibility.  
  
<a name="Programming_Languages_compare"></a>
## <a name="programming-languages"></a>Языки программирования  
<Active Accessibility основан на модели компонентных объектов (COM) с поддержкой двойных интерфейсов и, следовательно, программируется в языках C/C, Microsoft Visual Basic 6.0 и языках сценариев. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)](включая библиотеку поставщика стандартных элементов управления на стороне клиента) написана в управляемом коде, а клиентские приложения UI Automation наиболее легко запрограммированы с помощью C- или Visual Basic .NET. Поставщики автоматизации пользовательского интерфейса, которые являются реализациями интерфейса, могут быть написаны в управляемом коде или на C/C++.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>
## <a name="support-in-windows-presentation-foundation"></a>Поддержка в Windows Presentation Foundation  
 Windows Presentation Foundation (WPF) — это новая модель для создания пользовательских интерфейсов. Элементы WPF не содержат поддержки активной доступности; однако, они [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]поддерживают, которая включает в себя преодоление поддержки для клиентов Active Accessibility. Только клиенты, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] написанные специально для могут в полной мере воспользоваться возможностями доступности WPF, такими как богатая поддержка текста.  
  
<a name="Servers_and_Clients_compare"></a>
## <a name="servers-and-clients"></a>Серверы и клиенты  
 В Active Accessibility серверы и клиенты общаются напрямую, в основном благодаря реализации сервера `IAccessible`.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]основная служба находится между сервером (называемым поставщиком) и клиентом. Основная служба выполняет вызовы интерфейсов, реализованных поставщиками, и предоставляет дополнительные службы, такие как создание уникальных идентификаторов среды выполнения для элементов. Клиентские приложения используют функции библиотеки для вызова службы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Поставщики uI Automation могут предоставлять информацию клиентам Active Accessibility, а серверы Active Accessibility — клиентские приложения UI Automation. Однако, поскольку Active Accessibility не [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]предоставляет столько информации, сколько, две модели не полностью совместимы.  
  
<a name="UI_Elements_compare"></a>
## <a name="ui-elements"></a>Элементы пользовательского интерфейса  
 Active Accessibility [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] представляет элементы либо в виде интерфейса, `IAccessible` либо в виде идентификатора ребенка. Трудно сравнивать два указателя `IAccessible` , чтобы определить, ссылаются ли они на один и тот же элемент.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]каждый элемент представлен как объект <xref:System.Windows.Automation.AutomationElement> . Сравнение выполняется с помощью оператора равенства или метода <xref:System.Windows.Automation.AutomationElement.Equals%2A> ; в обоих способах сравниваются уникальные идентификаторы среды выполнения элементов.  
  
<a name="Tree_Views_and_Navigation_compare"></a>
## <a name="tree-views-and-navigation"></a>Представления в виде дерева и навигация  
 Элементы [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] на экране можно рассматривать как древовидную структуру с рабочим столом в качестве корня, окнами приложений в качестве непосредственных дочерних элементов и элементов в приложениях в качестве следующих потомков.  
  
 В Active Accessibility многие элементы автоматизации, которые не имеют отношения к конечным пользователям, подвергаются воздействию дерева. Клиентские приложения должны просмотреть все элементы, чтобы определить имеющие значение.  
  
 Клиентские приложения модели автоматизации пользовательского интерфейса видят [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] через отфильтрованное представление. Это представление содержит только элементы, представляющие интерес, т. е. те, которые предоставляют пользователю сведения или разрешают взаимодействие. Доступны предопределенные представления только элементов управления и только элементов содержимого; кроме того, приложения могут задавать специальные представления. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] упрощает задачу описания [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] для пользователя и помогает пользователю взаимодействовать с приложением.  
  
 Навигация между элементами в Active Accessibility является либо пространственной (например, перемещение милиемы влево на экране), либо логичной (например, переход омрачаем следующий элемент меню, либо следующий элемент в порядке вкладки в диалоговом поле), либо иерархической (например, иерархической ( например, перемещение первого ребенка в контейнере или от ребенка к его родителю). Иерархическая навигация осложняется тем, что дочерние элементы не всегда являются объектами, которые реализуют `IAccessible`.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]все элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] являются объектами <xref:System.Windows.Automation.AutomationElement> , которые поддерживают те же базовые функциональные возможности. (С точки зрения поставщика, они являются объектами, которые <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>реализуют интерфейс, унаследованный от .) Навигация в основном иерархична: от родителей к детям и от одного брата к другому. (Навигация между братьями и сестрами имеет логический элемент, так как может следовать порядку вкладки.) Вы можете перемещаться с любой отправной точки, используя любой отфильтрованный вид дерева, используя <xref:System.Windows.Automation.TreeWalker> класс. Вы также можете переходить к конкретному дочернему элементу или к потомкам с помощью методов <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> и <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; например, очень легко получить все элементы в диалоговом окне, поддерживающем указанный шаблон элемента управления.  
  
 Навигация [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] в более последовательной, чем в Active Accessibility. Некоторые элементы, такие как списки выпадающих и всплывающие окна, появляются дважды в дереве Active Accessibility, и навигация из них может иметь неожиданные результаты. На самом деле невозможно должным образом реализовать Активную доступность для управления арматом. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] допускает переподчинение и изменение расположения, так что элемент можно разместить в любом месте дерева, независимо от иерархии, обусловленной принадлежностью окон.  
  
<a name="Roles_and_Control_Types"></a>
## <a name="roles-and-control-types"></a>Роли и типы элементов управления  
 Active Accessibility `accRole` использует`IAccessible::get_actRole`свойство () для получения описания роли [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]элемента в , таких как ROLE_SYSTEM_SLIDER или ROLE_SYSTEM_MENUITEM. Роль элемента — это основной ключ к его доступным функциональным возможностям. Взаимодействие с элементом управления достигается с помощью фиксированных методов, таких как `IAccessible::accSelect` и `IAccessible::accDoDefaultAction`. Взаимодействие между клиентским приложением и [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ограничено тем, что может быть сделано с помощью `IAccessible`.  
  
 Напротив, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] во многом отделяет тип элемента управления (описываемый свойством <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> ) от его ожидаемой функциональности. Функциональность определяется шаблонами элементов управления, которые поддерживаются поставщиком через его реализацию специализированных интерфейсов. Шаблоны элементов управления можно объединить для описания полного набора функциональных возможностей, поддерживаемых конкретным элементом [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Некоторые поставщики обязаны поддерживать определенный шаблон элемента управления; например, поставщик флажка должен поддерживать шаблон элемента управления Toggle. Другие поставщики должны поддерживать хотя бы один набор шаблонов элементов управления; например, кнопки должны поддерживать Toggle или Invoke. Третьи поставщики вообще не поддерживают никакие шаблоны элементов управления; например, область, которую нельзя перемещать, изменять размер или закреплять, не имеет ни одного элемента управления.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] поддерживает пользовательские элементы управления, которые идентифицируются по свойству <xref:System.Windows.Automation.ControlType.Custom> и могут быть описаны свойством <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> .  
  
 В следующей таблице показано отображение ролей Active Accessibility для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] управления типами.  
  
|Роль активной доступности|Тип элемента управления[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
|ROLE_SYSTEM_PUSHBUTTON|Кнопка|  
|ROLE_SYSTEM_CLIENT|Календарь|  
|ROLE_SYSTEM_CHECKBUTTON|Флажок|  
|ROLE_SYSTEM_COMBOBOX|Поле со списком|  
|ROLE_SYSTEM_CLIENT|Другой|  
|ROLE_SYSTEM_LIST|Сетка данных|  
|ROLE_SYSTEM_LISTITEM|Элемент данных|  
|ROLE_SYSTEM_DOCUMENT|Документ|  
|ROLE_SYSTEM_TEXT|Изменить|  
|ROLE_SYSTEM_GROUPING|Группа|  
|ROLE_SYSTEM_LIST|Заголовок|  
|ROLE_SYSTEM_COLUMNHEADER|Элемент заголовка|  
|ROLE_SYSTEM_LINK|Hyperlink|  
|ROLE_SYSTEM_GRAPHIC|Образ —|  
|ROLE_SYSTEM_LIST|Список|  
|ROLE_SYSTEM_LISTITEM|Элемент списка|  
|ROLE_SYSTEM_MENUPOPUP|Меню|  
|ROLE_SYSTEM_MENUBAR|Строка меню|  
|ROLE_SYSTEM_MENUITEM|Элемент меню|  
|ROLE_SYSTEM_PANE|Панель|  
|ROLE_SYSTEM_PROGRESSBAR|Индикатор выполнения|  
|ROLE_SYSTEM_RADIOBUTTON|Переключатель|  
|ROLE_SYSTEM_SCROLLBAR|Полоса прокрутки|  
|ROLE_SYSTEM_SEPARATOR|Разделитель|  
|ROLE_SYSTEM_SLIDER|Ползунок|  
|ROLE_SYSTEM_SPINBUTTON|Spinner|  
|ROLE_SYSTEM_SPLITBUTTON|Разворачивающаяся кнопка|  
|ROLE_SYSTEM_STATUSBAR|Строка состояния|  
|ROLE_SYSTEM_PAGETABLIST|Вкладка|  
|ROLE_SYSTEM_PAGETAB|Элемент вкладки|  
|ROLE_SYSTEM_TABLE|Таблица|  
|ROLE_SYSTEM_STATICTEXT|текст|  
|ROLE_SYSTEM_INDICATOR|Бегунок|  
|ROLE_SYSTEM_TITLEBAR|Заголовок окна|  
|ROLE_SYSTEM_TOOLBAR|Панель инструментов|  
|Tool barROLE_SYSTEM_TOOLTIP|ToolTip|  
|ROLE_SYSTEM_OUTLINE|Дерево|  
|ROLE_SYSTEM_OUTLINEITEM|Элемент дерева|  
|ROLE_SYSTEM_WINDOW|Окно|  
  
 Дополнительные сведения о разных типах элементов управления см. в разделе [UI Automation Control Types](ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>
## <a name="states-and-properties"></a>Состояния и свойства  
 В Active Accessibility элементы поддерживают общий набор свойств, `accState`а некоторые свойства (например) должны описывать очень разные вещи, в зависимости от роли элемента. Серверы должны реализовывать все методы `IAccessible` , возвращающие свойство, даже те, которые не относятся к элементу.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]определяет гораздо больше свойств, некоторые из которых соответствуют состояниям в Active Accessibility. Одни свойства являются общими для всех элементов, а другие относятся к типам элементов управления и шаблонам элементов управления. Свойства различаются по уникальным идентификаторам, и большинство свойств можно получить с помощью одного метода, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> или <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Многие свойства легко извлекаются из методов доступа к свойствам <xref:System.Windows.Automation.AutomationElement.Current%2A> и <xref:System.Windows.Automation.AutomationElement.Cached%2A> .  
  
 Поставщик автоматизации пользовательского интерфейса не должен реализовывать ненужные свойства, он может просто возвращать значение `null` для всех свойств, которые он не поддерживает. Кроме того, основная служба [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] может получить некоторые свойства от поставщика окна по умолчанию, и эти свойства объединяются со свойствами, явно реализуемыми поставщиком.  
  
 Наряду с поддержкой множества дополнительных свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предлагает более высокую производительность, поскольку позволяет получать несколько свойств с помощью одного межпроцессного вызова.  
  
 В следующей таблице показано соответствие свойств в этих двух моделях.  
  
|Доступ к свойствам Active Access|Идентификатор свойства[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Remarks|  
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> либо <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|Если заданы оба свойства,`AccessKeyProperty` имеет более высокий приоритет.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>||  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Сопоставления ролей и типов элементов управления см. в предыдущей таблице.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>|Допустимо только для типов элементов управления, которые поддерживают ValuePattern или RangeValuePattern. Значения RangeValue нормализованы в значения от 0 до 100 для согласованности с поведением MSAA. Элементы Value используют строку.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]не поддерживается.|`accDescription` не имеет четкой спецификации в MSAA, в результате чего поставщики помещают в это свойство разные части сведений.|  
|`get_accHelpTopic`|В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]не поддерживается.||  
  
 В следующей [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] таблице показано, какие свойства соответствуют константам состояния Active Access.  
  
|Состояние активной доступности|Свойство [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Вызывает изменение состояния?|  
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------|----------------------------|  
|STATE_SYSTEM_CHECKED|Для флажка — <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Для переключателя — <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Да|  
|STATE_SYSTEM_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Collapsed>|Да|  
|STATE_SYSTEM_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Expanded> или <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>|Да|  
|STATE_SYSTEM_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|Нет|  
|STATE_SYSTEM_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|Нет|  
|STATE_SYSTEM_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> для пунктов меню|Нет|  
|STATE_SYSTEM_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True и <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> вызывает <xref:System.Windows.Automation.NoClickablePointException>|Нет|  
|STATE_SYSTEM_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> =<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|Нет|  
|STATE_SYSTEM_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> = <xref:System.Windows.Automation.ToggleState.Indeterminate>|Нет|  
|STATE_SYSTEM_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|Нет|  
|STATE_SYSTEM_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|Нет|  
|STATE_SYSTEM_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True|Нет|  
|STATE_SYSTEM_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|Нет|  
|STATE_SYSTEM_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=nameWithType>|Нет|  
|STATE_SYSTEM_SELECTABLE|<xref:System.Windows.Automation.SelectionItemPattern> поддерживается.|Нет|  
|STATE_SYSTEM_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Нет|  
|STATE_SYSTEM_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|Нет|  
|STATE_SYSTEM_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|Да|  
  
 Следующие состояния либо не были реализованы большинством серверов [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]управления Active Accessibility, либо не имеют эквивалента в .  
  
|Состояние активной доступности|Remarks|  
|-----------------------------------------------------------------------|-------------|  
|STATE_SYSTEM_BUSY|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_DEFAULT|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ANIMATED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_EXTSELECTABLE|Не широко реализованы серверами Active Accessibility|  
|STATE_SYSTEM_MARQUEED|Не широко реализованы серверами Active Accessibility|  
|STATE_SYSTEM_SELFVOICING|Не широко реализованы серверами Active Accessibility|  
|STATE_SYSTEM_TRAVERSED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ALERT_HIGH|Не широко реализованы серверами Active Accessibility|  
|STATE_SYSTEM_ALERT_MEDIUM|Не широко реализованы серверами Active Accessibility|  
|STATE_SYSTEM_ALERT_LOW|Не широко реализованы серверами Active Accessibility|  
|STATE_SYSTEM_FLOATING|Не широко реализованы серверами Active Accessibility|  
|STATE_SYSTEM_HOTTRACKED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_PRESSED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Полный список идентификаторов свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>
## <a name="events"></a>События  
 Механизм события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]в, в отличие от Active Accessibility, не опирается на разгром событий Windows (который тесно связан с оконными ручками) и не требует от клиентского приложения настройки крючков. Подписки на события можно детально настраивать не только для конкретных событий, но и для конкретных частей дерева. Поставщики также могут детально настраивать свой вызов событий, отслеживая, какие события прослушиваются.  
  
 Кроме того, клиентам стало проще получать элементы, которые вызывают события, поскольку они передаются напрямую в обратный вызов события. Свойства элемента автоматически предварительно выбираются, если запрос кэша был активен, когда клиент подписался на событие.  
  
 В следующей таблице показана корреспонденция Active Accessibility WinEvents и [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] событий.  
  
|WinEvent|Идентификатор события[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|--------------|--------------------------------------------------------------------------------------------|  
|EVENT_OBJECT_ACCELERATORCHANGE|Изменение свойства<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|  
|EVENT_OBJECT_CONTENTSCROLLED|Изменение свойства или  в связанных полосах прокрутки|  
|EVENT_OBJECT_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_DEFACTIONCHANGE|Нет эквивалента|  
|EVENT_OBJECT_DESCRIPTIONCHANGE|Нет точного эквивалента; возможно, изменение свойства <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> или <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT_OBJECT_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_OBJECT_HELPCHANGE|Изменение<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|  
|EVENT_OBJECT_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_LOCATIONCHANGE|Изменение свойства<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_OBJECT_NAMECHANGE|Изменение свойства<xref:System.Windows.Automation.AutomationElement.NameProperty>|  
|EVENT_OBJECT_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_REORDER|Не используется последовательно в Active Accessibility. Непосредственно соответствующее событие в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]не определено.|  
|EVENT_OBJECT_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT_OBJECT_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT_OBJECT_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT_OBJECT_SELECTIONWITHIN|Нет эквивалента|  
|EVENT_OBJECT_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_STATECHANGE|Различные события изменения свойств|  
|EVENT_OBJECT_VALUECHANGE|Изменены<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType> .|  
|EVENT_SYSTEM_ALERT|Нет эквивалента|  
|EVENT_SYSTEM_CAPTUREEND|Нет эквивалента|  
|EVENT_SYSTEM_CAPTURESTART|Нет эквивалента|  
|EVENT_SYSTEM_CONTEXTHELPEND|Нет эквивалента|  
|EVENT_SYSTEM_CONTEXTHELPSTART|Нет эквивалента|  
|EVENT_SYSTEM_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT_SYSTEM_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT_SYSTEM_DRAGDROPEND|Нет эквивалента|  
|EVENT_SYSTEM_DRAGDROPSTART|Нет эквивалента|  
|EVENT_SYSTEM_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_SYSTEM_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MINIMIZEEND|Изменение свойства<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT_SYSTEM_MINIMIZESTART|Изменение свойства<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|EVENT_SYSTEM_MOVESIZEEND|Изменение свойства<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_SYSTEM_MOVESIZESTART|Изменение свойства<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|  
|EVENT_SYSTEM_SCROLLINGEND|Изменение свойства или |  
|EVENT_SYSTEM_SCROLLINGSTART|Изменение свойства или |  
|EVENT_SYSTEM_SOUND|Нет эквивалента|  
|EVENT_SYSTEM_SWITCHEND|Нет эквивалента, но событие <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> сигнализирует, что новое приложение получило фокус|  
|EVENT_SYSTEM_SWITCHSTART|Нет эквивалента|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty>|  
|Нет эквивалента|Изменение свойства<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>|  
|Нет эквивалента|Событие<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent>|  
|Нет эквивалента|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>
## <a name="security"></a>Безопасность  
 В некоторых сценариях настройки `IAccessible` требуется перенос базового `IAccessible` и вызов через него. Это влияет на безопасность, поскольку частично доверенный компонент не должен быть посредником на пути кода.  
  
 В модели [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] устранена необходимость вызова поставщиками кода другого поставщика. Основная служба [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] выполняет все необходимое агрегирование.  
  
## <a name="see-also"></a>См. также раздел

- [Основы автоматизации uI](index.md)
