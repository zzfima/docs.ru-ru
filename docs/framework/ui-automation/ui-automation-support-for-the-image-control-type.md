---
title: Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления изображения
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Image control type
- control types, Image
- Image control type
ms.assetid: 4e0eeefb-e09b-46d2-b83b-0a7e35543ab8
ms.openlocfilehash: 52ccece88284724b03a6eb2d678bb27ab1d687c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446765"
---
# <a name="ui-automation-support-for-the-image-control-type"></a>Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления изображения
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления Image. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и шаблонов элементов управления.  
  
 Элементы управления "Изображение", используемые как значки, информационные рисунки и диаграммы, будут поддерживать тип элемента управления Image. Элементы управления "Изображение", используемые в качестве фона или водяных знаков, не будут поддерживать тип элемента управления Image.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления Image. Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "Изображение", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которое относится к элементам управления "Изображение" и описывает, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|------------------|------------------|  
|Изображение|Image (зависит от того, содержит ли изображение информацию (на основе значения свойства `IsContentElement` ))|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для типа элемента управления Image. Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|значения|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Активная точка элемента управления "Изображение" должна быть точкой внутри ограничивающего прямоугольника элемента управления "Изображение".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|См. примечания.|Если элемент управления может получать фокус клавиатуры, он должен поддерживать это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Свойство Name должно быть предоставлено для всех элементов управления "Изображение", содержащих информацию. Для программного доступа к этой информации необходимо предоставить текстовый эквивалент графики. Если элемент управления "Изображение" является исключительно декоративным, он должен отображаться только в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и не обязательно должен иметь имя. Инфраструктуры пользовательского интерфейса должны поддерживать в изображениях свойство ALT или "Замещающий текст", что можно задать в среде. Это свойство затем будет сопоставляться со свойством Name [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|См. примечания.|Если имеется статическая текстовая метка, то данное свойство должно предоставлять ссылку на этот элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Изображение|Это значение является одинаковым для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"изображение"|Локализованная строка, соответствующая типу элемента управления Image.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|См. примечания.|Элемент управления "Изображение" должен включаться в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , если он содержит существенные сведения, еще не предоставленные конечному пользователю.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элемент управления "Изображение" всегда включается в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|См. примечания.|Свойство HelpText представляет локализованную строку, которая описывает фактический внешний вид элемента управления (например, красный квадрат с белым символом "X") или другую подсказку, связанной с изображением.<br /><br /> Это свойство должно поддерживаться, если требуется длинное описание для передачи дополнительных сведений об элементе управления "Изображение". Например, для сложного графика или диаграммы. Это свойство сопоставляется с HTML-тегом LongDesc и тегом SVG (Scalable Vector Graphics — масштабируемый векторный рисунок) Desc. Разработчики, работающие с элементами управления "Изображение", должны поддерживать свойство, разрешающее задавать визуальное описание в элементе управления. Это свойство должно сопоставляться со свойством VisualDescription модели автоматизации пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>|См. примечания.|Если элемент управления "Изображение" представляет сведения о состоянии определенного элемента на экране, данный элемент управления должен находиться внутри этого элемента. Если изображение содержится в элементе, этот элемент должен поддерживать свойство состояния и вызывать соответствующие уведомления при изменении состояния.<br /><br /> Если изображение является автономным элементом управления и передает состояние, это свойство должно поддерживаться.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Изображение". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Зависит от обстоятельств|Элемент управления "Изображение" поддерживает шаблон Grid Item, если этот элемент управления находится внутри контейнера сетки.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Зависит от обстоятельств|Элемент управления "Изображение" поддерживает шаблон Table Item, если этот элемент управления находится внутри контейнера, имеющего элементы управления "Заголовок".|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Никогда|Если элемент управления "Изображение" содержит изображение, которое можно щелкнуть, он должен поддерживать тип элемента управления, поддерживающий шаблон Invoke, таких как тип элемента управления Button.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Никогда|Элементы управления "Изображение" не должны поддерживать шаблон Selection Item.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Изображение". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Никогда|Отсутствуют|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Никогда|Отсутствуют|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Никогда|Отсутствуют|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Никогда|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Обязательное значение|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное значение|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное значение|Отсутствуют|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType.Image>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
