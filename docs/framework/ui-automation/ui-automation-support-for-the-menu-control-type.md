---
title: Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления меню
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Menu
- UI Automation, Menu control type
- Menu control type
ms.assetid: 016323cb-f800-4938-b77b-2eb25d646090
ms.openlocfilehash: 155a2878dd71ab51f69d023594932ca715c073c4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040514"
---
# <a name="ui-automation-support-for-the-menu-control-type"></a>Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления меню
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] типа элемента управления Menu. Здесь описана древовидная структура [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] этого элемента управления и представлены свойства и шаблоны элементов управления для конкретных сценариев элементов управления.  
  
 Элемент управления "Меню" позволяет иерархически организовать элементы, связанные с командами и обработчиками событий. В типичном приложении Microsoft Windows строка меню содержит несколько кнопок меню (например, **файл**, **Правка**и **окно**), и каждая кнопка меню отображает меню. Меню содержит набор пунктов меню (таких как **Создать**, **Открыть**и **Закрыть**), которые можно развернуть, чтобы отобразить дополнительные пункты меню или выполнить определенное действие, нажав соответствующий пункт.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления Menu. Требования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "Список", будь это [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , относящиеся к элементам управления "Меню", и показывается, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление содержимого|  
|------------------|------------------|  
|Меню<br /><br /> -MenuItem (1 или несколько)|Неприменимо (если элемент управления "Меню" не является контекстным меню, родительским для объекта, который не является пунктом меню)<br /><br /> -MenuItem (1 или несколько)|  
  
 Элементы управления "Меню" всегда отображаются в представлении элемента управления и представлении содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Типы элементов управления Menu должны появляться над элементом управления, к которому относятся их сведения. Клиенты автоматизации пользовательского интерфейса должны прослушивать `MenuOpenedEvent` , чтобы убедиться, что они постоянно получают сведения, предоставляемые элементами управления "Меню". Особым случаем являются элементы управления "Контекстное меню". Они отображаются как дочерние элементы рабочего стола.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значения или определения которых особенно актуальны для типа элемента управления Menu. Дополнительные сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] свойствах см. в разделе [Свойства модели автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|значения|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Не поддерживается|Для элемента управления "Меню" не требуется задание свойства Name.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|С обычным элементом управления "Меню" не ожидается никаких меток.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Меню|Это значение является одинаковым для всех инфраструктур пользовательского интерфейса.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|False|Элемент управления "Меню" не включается в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Элемент управления "Меню" всегда включается в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 Для типа элемента управления Menu отсутствуют обязательные шаблоны элементов управления.  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Необходимые события модели автоматизации пользовательского интерфейса  
 Элементы управления "Меню" должны вызывать событие `MenuOpenedEvent` при отображении на экране. `MenuOpenedEvent` будет включать текст элемента управления. При исчезновении меню с экрана должно вызываться событие `MenuClosedEvent` .  
  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Меню". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка/значение|Примечания|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent>|Обязательное значение|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное значение|Отсутствуют|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное значение|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное значение|Отсутствуют|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное значение|Отсутствуют|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType.Menu>
- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
