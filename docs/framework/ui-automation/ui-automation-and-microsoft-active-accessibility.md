---
title: Модель автоматизации пользовательского интерфейса и Microsoft Active Accessibility
ms.date: 03/30/2017
helpviewer_keywords:
- Active Accessibility
- UI Automation, Active Accessibility compared to
- UI Automation, Microsoft Active Accessibility
- Active Accessibility, UI Automation compared to
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 1b7dbc8dffb15485ec035049d2da7aac6915eb58
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036218"
---
# <a name="ui-automation-and-microsoft-active-accessibility"></a>Модель автоматизации пользовательского интерфейса и Microsoft Active Accessibility
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Предыдущее решение по обеспечению доступности приложений —[!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] . [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] — это новая модель специальных возможностей для [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] , предназначенная для удовлетворения потребностей продуктов поддержки специальных возможностей и средств автоматизированного тестирования. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет множество улучшений по сравнению с [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
 В этом разделе рассматриваются основные функции [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и объясняется, как эти функции отличаются от [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
<a name="Programming_Languages_compare"></a>   
## <a name="programming-languages"></a>Языки программирования  
<[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] на основе [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)] с поддержкой сдвоенных интерфейсов и поэтому доступна для программирования на C/C++, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)]и языки сценариев. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (включая библиотеку поставщика на стороне клиента для стандартных элементов управления) записывается в управляемом коде, и клиентские приложения модели автоматизации пользовательского интерфейса проще всего программировать на C# или Visual Basic .NET. Поставщики автоматизации пользовательского интерфейса, которые являются реализациями интерфейса, могут быть написаны в управляемом коде или на C/C++.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## <a name="support-in-windows-presentation-foundation"></a>Поддержка в Windows Presentation Foundation  
 Windows Presentation Foundation (WPF) — это новая модель для создания пользовательских интерфейсов. В элементах[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] не предусмотрена собственная поддержка [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]; однако они поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], включая использование моста для клиентов [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] . Только клиенты, написанные специально для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , могут использовать все преимущества специальных возможностей [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], таких как расширенная поддержка текста.  
  
<a name="Servers_and_Clients_compare"></a>   
## <a name="servers-and-clients"></a>Серверы и клиенты  
 В [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]серверы и клиенты взаимодействуют напрямую, по большей части через серверную реализацию `IAccessible`.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]основная служба находится между сервером (называемым поставщиком) и клиентом. Основная служба выполняет вызовы интерфейсов, реализованных поставщиками, и предоставляет дополнительные службы, такие как создание уникальных идентификаторов среды выполнения для элементов. Клиентские приложения используют функции библиотеки для вызова службы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Поставщики автоматизации пользовательского интерфейса могут предоставлять сведения клиентам [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] , а серверы [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] — предоставлять сведения клиентским приложениям модели автоматизации пользовательского интерфейса. Однако поскольку [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] предоставляет меньше сведений, чем [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], эти две модели не являются полностью совместимыми.  
  
<a name="UI_Elements_compare"></a>   
## <a name="ui-elements"></a>Элементы пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] представляет элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] либо в виде интерфейса `IAccessible` , либо в виде идентификатора дочернего элемента. Трудно сравнивать два указателя `IAccessible` , чтобы определить, ссылаются ли они на один и тот же элемент.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]каждый элемент представлен как объект <xref:System.Windows.Automation.AutomationElement> . Сравнение выполняется с помощью оператора равенства или метода <xref:System.Windows.Automation.AutomationElement.Equals%2A> ; в обоих способах сравниваются уникальные идентификаторы среды выполнения элементов.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## <a name="tree-views-and-navigation"></a>Представления в виде дерева и навигация  
 Элементы [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] на экране можно рассматривать как древовидную структуру с рабочим столом в качестве корня, окнами приложений в качестве непосредственных дочерних элементов и элементов в приложениях в качестве следующих потомков.  
  
 В [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]многие элементы автоматизации, которые не касаются конечных пользователей, представлены в дереве. Клиентские приложения должны просмотреть все элементы, чтобы определить имеющие значение.  
  
 Клиентские приложения модели автоматизации пользовательского интерфейса видят [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] через отфильтрованное представление. Это представление содержит только элементы, представляющие интерес, т. е. те, которые предоставляют пользователю сведения или разрешают взаимодействие. Доступны предопределенные представления только элементов управления и только элементов содержимого; кроме того, приложения могут задавать специальные представления. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] упрощает задачу описания [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] для пользователя и помогает пользователю взаимодействовать с приложением.  
  
 Навигация по элементам в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]может быть пространственной (например, переход к элементу, который располагается слева на экране), логической (например, перемещение к следующему пункту меню или к следующему элементу в последовательности табуляции в диалоговом окне) или иерархической (например, перемещение в первый дочерний элемент в контейнере или от дочернего элемента к родительскому). Иерархическая навигация осложняется тем, что дочерние элементы не всегда являются объектами, которые реализуют `IAccessible`.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]все элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] являются объектами <xref:System.Windows.Automation.AutomationElement> , которые поддерживают те же базовые функциональные возможности. (С точки зрения поставщика они являются объектами, реализующими интерфейс, унаследованный от <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>.) Большей частью навигация является иерархической: от родительских элементов к дочерним и от одного элемента того же уровня к следующему. (Навигация между одноуровневыми элементами имеет логическую составляющую, так как она может следовать последовательности табуляции.) Вы можете переходить из любой начальной точки, используя любое отфильтрованное представление дерева, с помощью <xref:System.Windows.Automation.TreeWalker> класса. Вы также можете переходить к конкретному дочернему элементу или к потомкам с помощью методов <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> и <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; например, очень легко получить все элементы в диалоговом окне, поддерживающем указанный шаблон элемента управления.  
  
 Навигация в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] более последовательна, чем в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Некоторые элементы, например раскрывающиеся списки и всплывающие окна, появляются дважды в дереве [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] , и навигация из них может иметь непредсказуемые результаты. Фактически невозможно правильно реализовать [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] для элемента управления "Главная панель". [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] допускает переподчинение и изменение расположения, так что элемент можно разместить в любом месте дерева, независимо от иерархии, обусловленной принадлежностью окон.  
  
<a name="Roles_and_Control_Types"></a>   
## <a name="roles-and-control-types"></a>Роли и типы элементов управления  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] использует свойство `accRole` (`IAccessible::get_actRole`) для получения описания роли элемента в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], например ROLE_SYSTEM_SLIDER или ROLE_SYSTEM_MENUITEM. Роль элемента — это основной ключ к его доступным функциональным возможностям. Взаимодействие с элементом управления достигается с помощью фиксированных методов, таких как `IAccessible::accSelect` и `IAccessible::accDoDefaultAction`. Взаимодействие между клиентским приложением и [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ограничено тем, что может быть сделано с помощью `IAccessible`.  
  
 Напротив, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] во многом отделяет тип элемента управления (описываемый свойством <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> ) от его ожидаемой функциональности. Функциональность определяется шаблонами элементов управления, которые поддерживаются поставщиком через его реализацию специализированных интерфейсов. Шаблоны элементов управления можно объединить для описания полного набора функциональных возможностей, поддерживаемых конкретным элементом [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Некоторые поставщики обязаны поддерживать определенный шаблон элемента управления; например, поставщик флажка должен поддерживать шаблон элемента управления Toggle. Другие поставщики должны поддерживать хотя бы один набор шаблонов элементов управления; например, кнопки должны поддерживать Toggle или Invoke. Третьи поставщики вообще не поддерживают никакие шаблоны элементов управления; например, область, которую нельзя перемещать, изменять размер или закреплять, не имеет ни одного элемента управления.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] поддерживает пользовательские элементы управления, которые идентифицируются по свойству <xref:System.Windows.Automation.ControlType.Custom> и могут быть описаны свойством <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> .  
  
 В следующей таблице показано соответствие [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] ролей типам элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|Роль[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |Тип элемента управления[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
|ROLE_SYSTEM_PUSHBUTTON|Кнопка|  
|ROLE_SYSTEM_CLIENT|Календарь|  
|ROLE_SYSTEM_CHECKBUTTON|Флажок|  
|ROLE_SYSTEM_COMBOBOX|Поле со списком|  
|ROLE_SYSTEM_CLIENT|Другой|  
|ROLE_SYSTEM_LIST|Сетка данных|  
|ROLE_SYSTEM_LISTITEM|Элемент данных|  
|ROLE_SYSTEM_DOCUMENT|Document|  
|ROLE_SYSTEM_TEXT|Правка|  
|ROLE_SYSTEM_GROUPING|Группа|  
|ROLE_SYSTEM_LIST|Header|  
|ROLE_SYSTEM_COLUMNHEADER|Элемент заголовка|  
|ROLE_SYSTEM_LINK|Гиперссылка|  
|ROLE_SYSTEM_GRAPHIC|Изображение|  
|ROLE_SYSTEM_LIST|Список|  
|ROLE_SYSTEM_LISTITEM|Элемент списка|  
|ROLE_SYSTEM_MENUPOPUP|Меню|  
|ROLE_SYSTEM_MENUBAR|Строка меню|  
|ROLE_SYSTEM_MENUITEM|Элемент меню|  
|ROLE_SYSTEM_PANE|Панель|  
|ROLE_SYSTEM_PROGRESSBAR|Индикатор выполнения|  
|ROLE_SYSTEM_RADIOBUTTON|Переключатель|  
|ROLE_SYSTEM_SCROLLBAR|Полоса прокрутки|  
|ROLE_SYSTEM_SEPARATOR|Separator|  
|ROLE_SYSTEM_SLIDER|Slider|  
|ROLE_SYSTEM_SPINBUTTON|Spinner|  
|ROLE_SYSTEM_SPLITBUTTON|Разворачивающаяся кнопка|  
|ROLE_SYSTEM_STATUSBAR|Строка состояния|  
|ROLE_SYSTEM_PAGETABLIST|Tab|  
|ROLE_SYSTEM_PAGETAB|Элемент вкладки|  
|ROLE_SYSTEM_TABLE|Таблица|  
|ROLE_SYSTEM_STATICTEXT|Текста|  
|ROLE_SYSTEM_INDICATOR|Бегунок|  
|ROLE_SYSTEM_TITLEBAR|Заголовок окна|  
|ROLE_SYSTEM_TOOLBAR|Панель инструментов|  
|Tool barROLE_SYSTEM_TOOLTIP|ToolTip|  
|ROLE_SYSTEM_OUTLINE|Дерево|  
|ROLE_SYSTEM_OUTLINEITEM|Элемент дерева|  
|ROLE_SYSTEM_WINDOW|Окно|  
  
 Дополнительные сведения о разных типах элементов управления см. в разделе [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>   
## <a name="states-and-properties"></a>Состояния и свойства  
 В [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]элементы поддерживают общий набор свойств, и некоторые свойства (например `accState`) должны описывать очень разные вещи, в зависимости от роли элемента. Серверы должны реализовывать все методы `IAccessible` , возвращающие свойство, даже те, которые не относятся к элементу.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] определяет множество других свойств. Некоторые из них соответствует состояниям в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Одни свойства являются общими для всех элементов, а другие относятся к типам элементов управления и шаблонам элементов управления. Свойства различаются по уникальным идентификаторам, и большинство свойств можно получить с помощью одного метода, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> или <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Многие свойства легко извлекаются из методов доступа к свойствам <xref:System.Windows.Automation.AutomationElement.Current%2A> и <xref:System.Windows.Automation.AutomationElement.Cached%2A> .  
  
 Поставщик автоматизации пользовательского интерфейса не должен реализовывать ненужные свойства, он может просто возвращать значение `null` для всех свойств, которые он не поддерживает. Кроме того, основная служба [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] может получить некоторые свойства от поставщика окна по умолчанию, и эти свойства объединяются со свойствами, явно реализуемыми поставщиком.  
  
 Наряду с поддержкой множества дополнительных свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предлагает более высокую производительность, поскольку позволяет получать несколько свойств с помощью одного межпроцессного вызова.  
  
 В следующей таблице показано соответствие свойств в этих двух моделях.  
  
|Метод доступа к свойству[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |Идентификатор свойства[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Примечания|  
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> или <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|Если заданы оба свойства,`AccessKeyProperty` имеет более высокий приоритет.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>||  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Сопоставления ролей и типов элементов управления см. в предыдущей таблице.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>|Допустимо только для типов элементов управления, которые поддерживают ValuePattern или RangeValuePattern. Значения RangeValue нормализованы в значения от 0 до 100 для согласованности с поведением MSAA. Элементы Value используют строку.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]не поддерживается.|`accDescription` не имеет четкой спецификации в MSAA, в результате чего поставщики помещают в это свойство разные части сведений.|  
|`get_accHelpTopic`|В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]не поддерживается.||  
  
 В следующей таблице показано, какие свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] соответствуют константам состояний [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] .  
  
|Состояние[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Вызывает изменение состояния?|  
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------|----------------------------|  
|STATE_SYSTEM_CHECKED|Для флажка — <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Для переключателя — <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Y|  
|STATE_SYSTEM_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Collapsed>|Y|  
|STATE_SYSTEM_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Expanded> или <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>|Y|  
|STATE_SYSTEM_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|в|  
|STATE_SYSTEM_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|в|  
|STATE_SYSTEM_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> для пунктов меню|в|  
|STATE_SYSTEM_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True и <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> вызывает <xref:System.Windows.Automation.NoClickablePointException>|в|  
|STATE_SYSTEM_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> =<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|в|  
|STATE_SYSTEM_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> = <xref:System.Windows.Automation.ToggleState.Indeterminate>|в|  
|STATE_SYSTEM_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|в|  
|STATE_SYSTEM_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|в|  
|STATE_SYSTEM_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True|в|  
|STATE_SYSTEM_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|в|  
|STATE_SYSTEM_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=nameWithType>.|в|  
|STATE_SYSTEM_SELECTABLE|Поддерживается<xref:System.Windows.Automation.SelectionItemPattern> |в|  
|STATE_SYSTEM_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|в|  
|STATE_SYSTEM_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|в|  
|STATE_SYSTEM_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|Y|  
  
 Следующие состояния либо не реализованы большинством серверов управления [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] , либо не имеют эквивалента в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|Состояние[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |Примечания|  
|-----------------------------------------------------------------------|-------------|  
|STATE_SYSTEM_BUSY|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_DEFAULT|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ANIMATED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_EXTSELECTABLE|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_MARQUEED|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_SELFVOICING|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_TRAVERSED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ALERT_HIGH|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_ALERT_MEDIUM|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_ALERT_LOW|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_FLOATING|Нет широкой реализации серверами [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_HOTTRACKED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_PRESSED|Недоступно в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Полный список идентификаторов свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>   
## <a name="events"></a>События  
 Механизм событий в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в отличие от [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], не полагается на маршрутизацию событий Windows (которая тесно связана с дескрипторами окон) и не требует, чтобы клиентское приложение устанавливало обработчики. Подписки на события можно детально настраивать не только для конкретных событий, но и для конкретных частей дерева. Поставщики также могут детально настраивать свой вызов событий, отслеживая, какие события прослушиваются.  
  
 Кроме того, клиентам стало проще получать элементы, которые вызывают события, поскольку они передаются напрямую в обратный вызов события. Свойства элемента автоматически предварительно выбираются, если запрос кэша был активен, когда клиент подписался на событие.  
  
 В следующей таблице показано соответствие событий WinEvent [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] и событий [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|WinEvent|Идентификатор события[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |  
|--------------|--------------------------------------------------------------------------------------------|  
|EVENT_OBJECT_ACCELERATORCHANGE|Изменение свойства<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty> |  
|EVENT_OBJECT_CONTENTSCROLLED|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> или <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> в связанных полосах прокрутки|  
|EVENT_OBJECT_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_DEFACTIONCHANGE|Эквивалент отсутствует|  
|EVENT_OBJECT_DESCRIPTIONCHANGE|Нет точного эквивалента; возможно, изменение свойства <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> или <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT_OBJECT_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_OBJECT_HELPCHANGE|Изменение<xref:System.Windows.Automation.AutomationElement.HelpTextProperty> |  
|EVENT_OBJECT_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_LOCATIONCHANGE|Изменение свойства<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> |  
|EVENT_OBJECT_NAMECHANGE|Изменение свойства<xref:System.Windows.Automation.AutomationElement.NameProperty> |  
|EVENT_OBJECT_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_REORDER|Несогласованно используется в [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Непосредственно соответствующее событие в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]не определено.|  
|EVENT_OBJECT_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT_OBJECT_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT_OBJECT_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT_OBJECT_SELECTIONWITHIN|Эквивалент отсутствует|  
|EVENT_OBJECT_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_STATECHANGE|Различные события изменения свойств|  
|EVENT_OBJECT_VALUECHANGE|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType> и <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType> изменен|  
|EVENT_SYSTEM_ALERT|Эквивалент отсутствует|  
|EVENT_SYSTEM_CAPTUREEND|Эквивалент отсутствует|  
|EVENT_SYSTEM_CAPTURESTART|Эквивалент отсутствует|  
|EVENT_SYSTEM_CONTEXTHELPEND|Эквивалент отсутствует|  
|EVENT_SYSTEM_CONTEXTHELPSTART|Эквивалент отсутствует|  
|EVENT_SYSTEM_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT_SYSTEM_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT_SYSTEM_DRAGDROPEND|Эквивалент отсутствует|  
|EVENT_SYSTEM_DRAGDROPSTART|Эквивалент отсутствует|  
|EVENT_SYSTEM_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_SYSTEM_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MINIMIZEEND|Изменение свойства<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> |  
|EVENT_SYSTEM_MINIMIZESTART|Изменение свойства<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> |  
|EVENT_SYSTEM_MOVESIZEEND|Изменение свойства<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> |  
|EVENT_SYSTEM_MOVESIZESTART|Изменение свойства<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> |  
|EVENT_SYSTEM_SCROLLINGEND|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> или <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|EVENT_SYSTEM_SCROLLINGSTART|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> или <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|EVENT_SYSTEM_SOUND|Эквивалент отсутствует|  
|EVENT_SYSTEM_SWITCHEND|Нет эквивалента, но событие <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> сигнализирует, что новое приложение получило фокус|  
|EVENT_SYSTEM_SWITCHSTART|Эквивалент отсутствует|  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty> |  
|Эквивалент отсутствует|Изменение свойства<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> |  
|Эквивалент отсутствует|Событие<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent> |  
|Эквивалент отсутствует|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## <a name="security"></a>Безопасность  
 В некоторых сценариях настройки `IAccessible` требуется перенос базового `IAccessible` и вызов через него. Это влияет на безопасность, поскольку частично доверенный компонент не должен быть посредником на пути кода.  
  
 В модели [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] устранена необходимость вызова поставщиками кода другого поставщика. Основная служба [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] выполняет все необходимое агрегирование.  
  
## <a name="see-also"></a>См. также  
 [Основы модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/index.md)
