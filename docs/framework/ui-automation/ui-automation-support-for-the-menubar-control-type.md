---
title: Поддержка автоматизации пользовательского интерфейса для типа элемента управления MenuBar
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Menu Bar control type
- control types, Menu Bar
- Menu Bar control type
ms.assetid: c1202b21-c1f0-4560-853c-7b99bd73ad97
ms.openlocfilehash: a6727b298c6289297fe049ffa4e64623bc9b711a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778446"
---
# <a name="ui-automation-support-for-the-menubar-control-type"></a>Поддержка автоматизации пользовательского интерфейса для типа элемента управления MenuBar
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления <xref:System.Windows.Automation.ControlType.MenuBar> . В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 Элементы управления "Строка меню" являются примерами элементов управления, реализующих тип элемента управления MenuBar. С помощью строк меню пользователи могут активировать команды и параметры, содержащиеся в приложении.  
  
 В следующих разделах описывается требуемая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления MenuBar. Требования к [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "список", будь то [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 или Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления "Строка меню", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление контента|  
|------------------|------------------|  
|MenuBar<br /><br /> -MenuItem (1 или более)<br />— Другие элементы управления (0 или многие)|MenuBar<br /><br /> -MenuItem (1 или более)<br />— Другие элементы управления (0 или многие)|  
  
 Элементы управления "Строка меню" могут содержать в своей структуре другие элементы управления, такие как "Поле ввода" и "Поле со списком". Эти дополнительные элементы управления соответствуют "другим элементам управления", перечисленным выше в представлениях элемента управления и содержимого.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для элементов управления "Строка меню". Дополнительные сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] свойствах см. в разделе [Свойства модели автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|{2&gt;Value&lt;2}|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Значение, представляемое этим свойством, должно включать все содержащиеся в нем элементы управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Элементу управления "Строка меню" имя не требуется, кроме случая, когда в приложении имеется несколько строк меню. Если в приложении имеется несколько строк меню, то это свойство должно использоваться для предоставления различающихся имен, например "Форматирование" или "Структурирование".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Элементы управления "Строка меню" никогда не имеют метки.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|MenuBar|Это значение одинаково для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"строка меню"|Локализованная строка, соответствующая типу элемента управления MenuBar.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Да|Элемент управления "Строка меню" всегда включается в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Да|Элемент управления "Строка меню" всегда включается в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|См. примечания.|Значение этого свойства зависит от того, можно ли видеть элемент управления на экране.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.OrientationProperty>|Зависит от обстоятельств|Это свойство показывает, является ли элемент управления "Строка меню" горизонтальным или вертикальным.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Да|Элементы управления "Строка меню" являются фокусируемыми с помощью клавиатуры, так как элементы управления, содержащиеся в них, могут принимать фокус клавиатуры.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|См. примечания.|Ни в каких случаях элементу управления "Строка меню" текст справки не требуется.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>|`Null`|Строки меню никогда не имеют клавиш быстрого доступа.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>|ALT|Нажатие клавиши ALT должно всегда переводить фокус в строку меню в приложении.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться элементами управления "Строка меню". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Зависит от обстоятельств|Если элемент управления можно разворачивать и сворачивать, реализуйте <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.|  
|<xref:System.Windows.Automation.Provider.IDockProvider>|Зависит от обстоятельств|Если элемент управления можно прикреплять к разным частям экрана, реализуйте <xref:System.Windows.Automation.Provider.IDockProvider>.|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|Зависит от обстоятельств|Если элемент управления можно перемещать, поворачивать или изменять его размер, он должен реализовывать <xref:System.Windows.Automation.Provider.ITransformProvider>.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Строка меню". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка/значение|Примечания|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty>|Зависит от обстоятельств|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное|Нет|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Automation.ControlType.MenuBar>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
