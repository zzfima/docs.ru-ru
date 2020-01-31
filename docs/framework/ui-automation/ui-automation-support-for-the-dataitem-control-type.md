---
title: Поддержка автоматизации пользовательского интерфейса для элемента управления типа DataItem
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Data Item control type
- Data Item control type
- control types, Data Item
ms.assetid: 181708fd-2595-4c43-9abd-75811627d64c
ms.openlocfilehash: d950783b91252f1bcbb1ff818aff5cf8472218b7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789533"
---
# <a name="ui-automation-support-for-the-dataitem-control-type"></a>Поддержка автоматизации пользовательского интерфейса для элемента управления типа DataItem
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] типа элемента управления DataItem. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 Запись в списке контактов является примером элемента управления DataItem. Элемент управления DataItem содержит сведения, представляющие интерес для конечного пользователя. Он более сложный, чем обычный элемент списка, так как содержит более ценные сведения.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления DataItem. Требования к [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления DataItem, будь то [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 или Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления DataItem, и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Дерево[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление элемента управления|Дерево[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление содержимого|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataItem<br /><br /> — Изменяется (0 или более; может быть структурировано в иерархии)|DataItem<br /><br /> — Изменяется (0 или более; может быть структурировано в иерархии)|  
  
 Элемент данных в сетке данных может поддерживать множество объектов, в том числе еще один уровень элементов данных или определенные элементы сетки, такие как текст, изображения или элементы управления "Поле ввода". Если элемент данных имеет определенную роль объекта, этот элемент должен представляться как определенный тип элемента управления; например, тип элемента управления ListItem для элемента данных, доступного для выбора в сетке.  
  
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства, значение или определение которых в первую очередь относится к элементам управления DataItem. Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Идентификаторы|{2&gt;Value&lt;2}|Примечания|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Поддерживается при наличии ограничивающего прямоугольника. Если не все точки внутри ограничивающего прямоугольника являются интерактивными и выполняется специализированная проверка на наличие данных, выполните переопределение и предоставьте интерактивную точку.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataItem|Это значение одинаково для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Да|Элемент управления DataItem всегда должен быть содержимым.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Да|Элемент управления DataItem всегда должен быть элементом управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>|См. примечания.|Если элемент управления содержит состояние, которое обновляется динамически, то это свойство должно поддерживаться, чтобы специальные возможности могли получать обновления при изменении состояния элемента.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|См. примечания.|Это строковое значение, передающее конечному пользователю базовый объект, который этот элемент представляет. Примерами являются "Файл мультимедиа" или "Контакт".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Элементы управления DataItem не имеют меток со статическим текстом.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"элемент данных"|Локализованная строка, соответствующая типу элемента управления DataItem.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Элемент управления DataItem всегда содержит основной текстовый элемент, имеющий отношение к тому, что пользователь будет воспринимать как семантический идентификатор для элемента.|  
  
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления DataItem. Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Зависит от обстоятельств|Если элемент данных можно разворачивать и сворачивать для отображения или скрытия информации, должен поддерживаться шаблон Expand Collapse.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Зависит от обстоятельств|Элементы данных будет поддерживать шаблон Grid Item (элемент сетки), когда коллекция элементов данных доступна в контейнере, в котором можно выполнять пространственную навигацию от элемента к элементу.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Зависит от обстоятельств|Все элементы данных поддерживают возможность прокручивания в представлении с помощью шаблона Scroll Item, когда их контейнер данных содержит больше элементов, чем может поместиться на экране.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Да|Все элементы данных должны поддерживать шаблон Selection Item, чтобы указывать, когда элемент выбран.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Зависит от обстоятельств|Если элемент данных содержится в типе элемента управления Data Grid, он будет поддерживать этот шаблон.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Зависит от обстоятельств|Если элемент данных содержит состояние, которое может быть циклически пройдено.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Зависит от обстоятельств|Если основной текст элемента данных является редактируемым, то должен поддерживаться шаблон Value.|  
  
## <a name="working-with-data-items-in-large-lists"></a>Работа с элементами данных в больших списках  
 Большие списки часто являются данными, виртуализированными в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] для улучшения производительности. Из-за этого клиент автоматизации пользовательского интерфейса не может использовать функциональность запроса [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для очистки содержимого полного дерева таким же образом, как в других контейнерах элементов. Клиент должен прокрутить элемент в представление (или развернуть элемент управления, чтобы отобразить все важные параметры) до получения доступа к полному набору сведений из элемента данных.  
  
 При вызове `SetFocus` в элементе [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для элемента данных обращение к Microsoft Windows Explorer будет успешным, и фокус будет установлен на изменение в поддереве элемента данных.  
  
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления DataItem. Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Обязательное|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное|Нет|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty>|Зависит от обстоятельств|Нет|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Обязательное|Нет|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Обязательное|Нет|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|Зависит от обстоятельств|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>|Зависит от обстоятельств|Нет|  
  
## <a name="dataitem-control-type-example"></a>Пример элемента управления DataItem  
 На следующем рисунке показан тип элемента управления DataItem в элементе управления представления списка с поддержкой подробных сведений для столбцов.  
  
 ![Рисунок элемента управления "представление списка" с двумя элементами данных](./media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 Представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементу управления DataItem, показаны ниже. Шаблоны элементов управления для каждого элемента автоматизации отображаются в круглых скобках. Группа "Contoso" также является частью сетки элемента управления ведущего приложения Data Grid.  
  
|Дерево[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление элемента управления|Дерево[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — представление содержимого|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|— Группа Contoso (таблица, сетка)<br />-DataItem "Accounts. doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-Image "Accounts. doc"<br />-Edit "имя" (TableItem, GridItem, value "Accounts. doc")<br />-Изменить "Дата изменения" (TableItem, GridItem, value "8/25/2006 3:29 PM")<br />-Edit "размер" (GridItem, TableItem, value "11,0 КБ)"<br />-DataItem "Accounts. doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   ...|— Группа Contoso (таблица, сетка)<br />-DataItem "Accounts. doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-Image "Accounts. doc"<br />-Edit "имя" (TableItem, GridItem, value "Accounts. doc")<br />-Изменить "Дата изменения" (TableItem, GridItem, value "8/25/2006 3:29 PM")<br />-Edit "размер" (GridItem, TableItem, value "11,0 КБ)"<br />-DataItem "Accounts. doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   …|  
  
 Если сетка представляет список выбираемых элементов, соответствующие элементы пользовательского интерфейса могут быть представлены типом элемента управления ListItem, а не DataItem. В предыдущем примере элементы DataItem (Accounts Receivable.doc и Accounts Payable.doc) в в элементе Group (Contoso) можно улучшить, представив их как элементы управления типа ListItem, поскольку этот тип уже поддерживает шаблон элемента управления SelectionItem.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Automation.ControlType.DataItem>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
