---
title: Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ComboBox
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Combo Box
- UI Automation, Combo Box control type
- ComboBox controls
ms.assetid: bb321126-4770-41da-983a-67b7b89d45dd
ms.openlocfilehash: 6cdabc3b8d55f6f1b4568b513cbb812e043db689
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741686"
---
# <a name="ui-automation-support-for-the-combobox-control-type"></a>Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ComboBox
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] типа элемента управления ComboBox. В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]тип элемента управления — это набор условий, которым должен удовлетворять элемент управления для использования свойства <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Условия включают конкретные правила для древовидной структуры [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значений свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , шаблонов элементов управления т событий [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Поле со списком представляет собой список, объединенный со статическим элементом управления или элементом управления "Поле ввода", который отображает выбранный элемент в списке поля со списком. Часть списка этого элемента управления отображается все время или появляется только при нажатии пользователем стрелки раскрывающегося списка (являющейся кнопкой) рядом с элементом управления. Если поле выбора является элементом управления "Поле ввода", пользователь может ввести сведения, которых нет в списке; в противном случае пользователь может только выбирать элементы в списке.  
  
 В следующих разделах описывается необходимая древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , свойства, шаблоны элементов управления и события для типа элемента управления ComboBox. Требования к [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] применяются ко всем элементам управления "поле со списком", будь то [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 или [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Требуемая древовидная структура модели автоматизации пользовательского интерфейса  
 В следующей таблице описывается представление элемента управления и представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которое относится к элементам управления "Поле со списком" и описывает, что может содержаться в каждом представлении. Дополнительные сведения о дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Представление элемента управления|Представление контента|  
|------------------|------------------|  
|ComboBox<br /><br /> -Edit (0 или 1)<br />-List (1)<br />— Элемент списка (дочерний объект списка; 0 – несколько)<br />Кнопка (1)|ComboBox<br /><br /> — Элемент списка (от 0 до многих)|  
  
 Элемент представления "Поле ввода" в представлении элемента управления для поля со списком необходим только в том случае, если в поле со списком можно добавлять какие-либо введенные данные, как в случае поля со списком в диалоговом окне "Выполнить".  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Требуемые свойства модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , значение или определение которых в первую очередь относится к элементам управления "Поле со списком". Дополнительные сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Свойство[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|{2&gt;Value&lt;2}|Примечания|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|См. примечания.|Значение этого свойства должно быть уникальным среди всех элементов управления в приложении.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|См. примечания.|Внешний прямоугольник, содержащий весь элемент управления.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|См. примечания.|Поддерживается при наличии ограничивающего прямоугольника. Если не все точки внутри ограничивающего прямоугольника являются интерактивными и выполняется специализированная проверка на наличие данных, выполните переопределение и предоставьте интерактивную точку.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ComboBox|Это значение является одинаковым для всех инфраструктур [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|См. примечания.|Текст справки для элементов управления "Поле со списком" должен объяснять, почему пользователю предлагается выбрать вариант из поля со списком. Этот текст совпадает со сведениями, которые предоставляются в подсказке. Например, "Выберите элемент, чтобы установить разрешение экрана монитора".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Да|Элементы управления "Поле со списком" всегда включаются в представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Да|Элементы управления "Поле со списком" всегда включаются в представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Да|Элементы управления "Поле со списком" предоставляют набор элементов из контейнера выбора. Элемент управления "Поле со списком" может получать фокус клавиатуры, хотя когда клиент автоматизации пользовательского интерфейса устанавливает фокус в поле со списком, любой элемент в поддереве этого поля со списком может получить фокус.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|См. примечания.|Элементы управления "Поле со списком" обычно имеют метку со статическим текстом, на который ссылается это свойство.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"поле со списком"|Локализованная строка, соответствующая типу элемента управления ComboBox.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|См. примечания.|Элемент управления "Поле со списком" обычно получает свое имя из элемента управления "Статический текст".|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Необходимые шаблоны элементов управления модели автоматизации пользовательского интерфейса  
 В следующей таблице перечислены шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Поле со списком". Дополнительные сведения о шаблонах элементов управления см. в разделе [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Шаблон элемента управления|Поддержка|Примечания|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Да|Элемент управления "Поле со списком" всегда должен содержать кнопку раскрывающегося списка, чтобы быть полем со списком.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Да|Отображает текущий выбор в поле со списком. Эта поддержка делегируется списку под полем со списком.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Зависит от обстоятельств|Если поле со списком имеет возможность принимать произвольные текстовые значения, должен поддерживаться шаблон Value. Этот шаблон предоставляет возможность программно задавать содержимое строки поля со списком. Если шаблон Value не поддерживается, это означает, что пользователь должен выбирать из элементов списка в поддереве поля со списком.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Никогда.|Шаблон Scroll никогда не поддерживается в поле со списком напрямую. Он поддерживается, если можно прокручивать список, содержащийся в поле со списком. Он может поддерживаться только тогда, когда список отображается на экране.|  
  
<a name="Required_Events"></a>   
## <a name="required-events"></a>Обязательные события  
 В следующей таблице перечислены события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , которые должны поддерживаться всеми элементами управления "Поле со списком". Дополнительные сведения о событиях см. в разделе [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|Событие[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Поддержка|Примечания|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>|Обязательное|Нет|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty>|Обязательное|Нет|  
|Событие изменения свойства<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>|Зависит от обстоятельств|Если элемент управления поддерживает шаблон Value, то он должен поддерживать данное событие.|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Automation.ControlType.ComboBox>
- [Общие сведения о типах элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types-overview.md)
- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
