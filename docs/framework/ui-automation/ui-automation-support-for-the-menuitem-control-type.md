---
title: Поддержка автоматизации пользовательского интерфейса для типа элемента управления MenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Menu Item
- Menu Item control type
- UI Automation, Menu Item control type
ms.assetid: 54bce311-3d23-40b9-ba90-1bdbdaf8fbba
ms.openlocfilehash: c65e30ffea64a9b577cfee7535fd92e489bc7632
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446704"
---
# <a name="ui-automation-support-for-the-menuitem-control-type"></a>Поддержка автоматизации пользовательского интерфейса для типа элемента управления MenuItem

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).

В этом разделе содержатся сведения о поддержке в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] типа элемента управления MenuItem. Здесь описана древовидная структура [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] этого элемента управления и представлены свойства и шаблоны элементов управления, которые необходимы для типа элемента управления MenuItem.

Элемент управления "Меню" позволяет иерархически организовать элементы, связанные с командами и обработчиками событий. В типичном приложении Microsoft Windows строка меню содержит несколько пунктов меню (например, **файл**, **Правка**и **окно**), и каждый пункт меню отображает меню. Меню содержит набор пунктов меню (таких как **Создать**, **Открыть**и **Закрыть**), которые можно развернуть, чтобы отобразить дополнительные пункты меню или выполнить определенное действие, нажав соответствующий пункт. Пункт меню может размещаться в меню, строке меню или панели инструментов.

В следующих разделах описывается требуемая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления MenuItem. Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "Список", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса

В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления "Пункт меню", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).

|Представление элемента управления|Представление содержимого|
|------------------|------------------|
|MenuItem "Справка"<br /><br /> <ul><li>Menu (подменю из меню "Справка")<br /><br /> <ul><li>MenuItem "Вызов справки"</li><li>MenuItem "О Блокноте"</li></ul></li></ul>|MenuItem "Справка"<br /><br /> -MenuItem "разделы справки"<br />-MenuItem "о Блокноте"|

Представление элемента управления "Пункт меню" имеет древовидную структуру [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , как показано выше. Обратите внимание, что пункт меню " **Справка** " позволяет лучше проиллюстрировать структуру в типичном меню до иерархии подменю.

В представлении содержимого отсутствует элемент Menu из дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , потому что он не передает полезные сведения для конечного пользователя.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса

В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значение или определение которых в первую очередь относится к элементам управления "Пункт меню". Дополнительные сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] свойствах см. в разделе [Свойства модели автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md).

|Свойство|значения|Описание|
|--------------|-----------|-----------------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Поддерживается при наличии ограничивающего прямоугольника. Если не все точки внутри ограничивающего прямоугольника являются интерактивными и выполняется специализированная проверка на наличие данных, выполните переопределение и предоставьте интерактивную точку.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Элемент управления "Пункт меню" включается в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и автоматически получает метку в виде имени.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Без метки.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|MenuItem|Это значение одинаково для всех инфраструктур пользовательского интерфейса.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"пункт меню"|Локализованная строка, соответствующая типу элемента управления MenuItem.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Да|Элемент управления "Пункт меню" никогда не включается в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Да|Элемент управления "Пункт меню" всегда должен включаться в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса

В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться элементами управления "Пункт меню". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).

|Свойство шаблона элемента управления|Поддержка|Примечания|
|------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Зависит от обстоятельств|Если элемент управления можно разворачивать и сворачивать, реализуйте <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.|
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Зависит от обстоятельств|Если элемент управления выполняет единственное действие или команду, реализуйте <xref:System.Windows.Automation.Provider.IInvokeProvider>.|
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Зависит от обстоятельств|Если элемент управления представляет параметр, который можно включить или отключить, реализуйте <xref:System.Windows.Automation.Provider.IToggleProvider>.|
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Зависит от обстоятельств|Если элемент управления используется для выбора из списка пунктов меню, реализуйте <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.|

<a name="UI_Automation_Events_for_Menu_Item"></a>

## <a name="ui-automation-events-for-menu-item"></a>События модели автоматизации пользовательского интерфейса для пункта меню

В следующей таблице перечислены события [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , связанные с элементом управления "Пункт меню".

|событие|Поддержка|Объяснение|
|-----------|-------------|-----------------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Зависит от обстоятельств|Должно вызываться, если элемент управления поддерживает шаблон элемента управления Invoke.|
|Событие изменения свойства<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|Зависит от обстоятельств|Должно вызываться, если элемент управления поддерживает шаблон элемента управления Toggle.|
|Событие изменения свойства<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty>|Зависит от обстоятельств|Должно вызываться, если элемент управления поддерживает шаблон элемента управления Expand Collapse.|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Зависит от обстоятельств|Нет.|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса

В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Пункт меню". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).

|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка/значение|Примечания|
|---------------------------------------------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Зависит от обстоятельств|Нет|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Зависит от обстоятельств|Нет|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Зависит от обстоятельств|Нет|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Зависит от обстоятельств|Нет|
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное|Нет|
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное|Нет|
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное|Нет|
|Событие изменения свойства<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty>|Зависит от обстоятельств|Нет|
|Событие изменения свойства<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|Зависит от обстоятельств|Нет|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное|Нет|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное|Нет|

<a name="Legacy_Issues"></a>

## <a name="legacy-issues"></a>Проблемы прежних версий

Шаблон Toggle будет поддерживаться только в том случае, если пункт меню [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] отмечен и если можно программными средствами определить необходимость поддержки шаблона Toggle. Поскольку пункт меню [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] не раскрывает, имеет ли он возможность быть отмеченным, шаблон Invoke будет поддерживаться, когда этот пункт меню не отмечен. Исключение будет сделано, чтобы всегда поддерживать шаблон Invoke, даже для пунктов меню, которые должны поддерживать только шаблон Toggle. Это делается для того, чтобы клиенты ошибочно не думали, что элемент, который поддерживал шаблон Invoke (когда пункт меню не был отмечен), больше не поддерживает этот шаблон, когда становится отмеченным.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType.MenuItem>
- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
