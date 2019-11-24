---
title: Реализация шаблона элемента управления Value модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
ms.openlocfilehash: c178283b18aaf2c406292d9ab7e12a24c882c102
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447046"
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a>Реализация шаблона элемента управления Value модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IValueProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.ValuePattern> используется для поддержки элементов управления, имеющих встроенное значение, которое не попадает в диапазон и может быть представлено в виде строки. Эта строка может быть редактируемой в зависимости от элемента управления и его параметров. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Value обратите внимание на следующие правила и соглашения.  
  
- Элементы управления, такие как <xref:System.Windows.Automation.ControlType.ListItem> и <xref:System.Windows.Automation.ControlType.TreeItem> , должны поддерживать шаблон <xref:System.Windows.Automation.ValuePattern> , если значение любого из элементов можно изменять независимо от текущего режима редактирования элемента управления. Родительский элемент управления также должен поддерживать шаблон <xref:System.Windows.Automation.ValuePattern> , если дочерние элементы являются редактируемыми.  
  
 ![Editable list item.](./media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")  
Пример редактируемого элемента списка  
  
- Однострочные элементы управления "Поле ввода" поддерживают программный доступ к своему содержимому путем реализации <xref:System.Windows.Automation.Provider.IValueProvider>. Однако многострочные элементы управления "Поле ввода" не реализуют <xref:System.Windows.Automation.Provider.IValueProvider>; вместо этого они предоставляют доступ к своему содержимому путем реализации <xref:System.Windows.Automation.Provider.ITextProvider>.  
  
- Для получения текстового содержимого многострочного элемента управления "Поле ввода" этот элемент управления должен реализовывать <xref:System.Windows.Automation.Provider.ITextProvider>. Однако <xref:System.Windows.Automation.Provider.ITextProvider> не поддерживает установку значения элемента управления.  
  
- <xref:System.Windows.Automation.Provider.IValueProvider> не поддерживает извлечение сведений о форматировании или значений подстроки. Реализуйте <xref:System.Windows.Automation.Provider.ITextProvider> в этих сценариях.  
  
- <xref:System.Windows.Automation.Provider.IValueProvider> must be implemented by controls such as the **Color Picker** selection control from Microsoft Word (illustrated below), which supports string mapping between a color value (for example, "yellow") and an equivalent internal RGB structure.  
  
 ![Color picker with yellow highlighted.](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Пример сопоставления строки настройки цвета  
  
- Элемент управления должен иметь свойство <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> , установленное в значение `true` , и свойство <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> , установленное в значение `false` , перед разрешением вызова метода <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-ivalueprovider"></a>Обязательные члены для IValueProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IValueProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|свойство;|Отсутствуют|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|свойство;|Отсутствуют|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|Метод|Отсутствуют|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> -   If locale-specific information is passed to a control in an incorrect format such as an incorrectly formatted date.|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> -   If a new value cannot be converted from a string to a format the control recognizes.|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> -   When an attempt is made to manipulate a control that is not enabled.|  
  
## <a name="see-also"></a>См. также

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [ValuePattern Insert Text Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
