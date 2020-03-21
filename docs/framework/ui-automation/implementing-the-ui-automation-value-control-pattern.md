---
title: Реализация шаблона элемента управления Value модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
ms.openlocfilehash: eb77f26bbe3546a3f90804c3648f8547fb6abad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180091"
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
  
 ![Редактируемый элемент списка.](./media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")  
Пример редактируемого элемента списка  
  
- Однострочные элементы управления "Поле ввода" поддерживают программный доступ к своему содержимому путем реализации <xref:System.Windows.Automation.Provider.IValueProvider>. Однако многострочные элементы управления "Поле ввода" не реализуют <xref:System.Windows.Automation.Provider.IValueProvider>; вместо этого они предоставляют доступ к своему содержимому путем реализации <xref:System.Windows.Automation.Provider.ITextProvider>.  
  
- Для получения текстового содержимого многострочного элемента управления "Поле ввода" этот элемент управления должен реализовывать <xref:System.Windows.Automation.Provider.ITextProvider>. Однако <xref:System.Windows.Automation.Provider.ITextProvider> не поддерживает установку значения элемента управления.  
  
- <xref:System.Windows.Automation.Provider.IValueProvider> не поддерживает извлечение сведений о форматировании или значений подстроки. Реализуйте <xref:System.Windows.Automation.Provider.ITextProvider> в этих сценариях.  
  
- <xref:System.Windows.Automation.Provider.IValueProvider>должны быть реализованы с помощью элементов управления, таких как управление **выбором Color Picker** от Microsoft Word (иллюстрированный ниже), который поддерживает строку отображение между значением цвета (например, "желтый") и эквивалентной внутренней структурой RGB.  
  
 ![Палитра с отмеченным желтым цветом.](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Пример сопоставления строки настройки цвета  
  
- Элемент управления должен иметь свойство <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> , установленное в значение `true` , и свойство <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> , установленное в значение `false` , перед разрешением вызова метода <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>
## <a name="required-members-for-ivalueprovider"></a>Обязательные члены для IValueProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IValueProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|Свойство|None|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|Свойство|None|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|Метод|None|  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> - Если информация, связанная с локальной информацией, передается в элемент управления в неправильном формате, например неправильно отформатированная дата.|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> - Если новое значение не может быть преобразовано из строки в формат, который распознает элемент управления.|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> - При попытке манипулировать элементом управления, который не включен.|  
  
## <a name="see-also"></a>См. также раздел

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Образец текста ValuePattern Вставить](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
