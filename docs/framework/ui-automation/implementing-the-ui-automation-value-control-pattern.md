---
title: Реализация шаблона элемента управления Value модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 383145bdf4e190a7e2a49d2c5dc632f678bbb4ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743664"
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a>Реализация шаблона элемента управления Value модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IValueProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.ValuePattern> используется для поддержки элементов управления, имеющих встроенное значение, которое не попадает в диапазон и может быть представлено в виде строки. Эта строка может быть редактируемой в зависимости от элемента управления и его параметров. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Value обратите внимание на следующие правила и соглашения.  
  
-   Элементы управления, такие как <xref:System.Windows.Automation.ControlType.ListItem> и <xref:System.Windows.Automation.ControlType.TreeItem> , должны поддерживать шаблон <xref:System.Windows.Automation.ValuePattern> , если значение любого из элементов можно изменять независимо от текущего режима редактирования элемента управления. Родительский элемент управления также должен поддерживать шаблон <xref:System.Windows.Automation.ValuePattern> , если дочерние элементы являются редактируемыми.  
  
 ![Редактируемый элемент списка. ](../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")  
Пример редактируемого элемента списка  
  
-   Однострочные элементы управления "Поле ввода" поддерживают программный доступ к своему содержимому путем реализации <xref:System.Windows.Automation.Provider.IValueProvider>. Однако многострочные элементы управления "Поле ввода" не реализуют <xref:System.Windows.Automation.Provider.IValueProvider>; вместо этого они предоставляют доступ к своему содержимому путем реализации <xref:System.Windows.Automation.Provider.ITextProvider>.  
  
-   Для получения текстового содержимого многострочного элемента управления "Поле ввода" этот элемент управления должен реализовывать <xref:System.Windows.Automation.Provider.ITextProvider>. Однако <xref:System.Windows.Automation.Provider.ITextProvider> не поддерживает установку значения элемента управления.  
  
-   <xref:System.Windows.Automation.Provider.IValueProvider> не поддерживает извлечение сведений о форматировании или значений подстроки. Реализуйте <xref:System.Windows.Automation.Provider.ITextProvider> в этих сценариях.  
  
-   <xref:System.Windows.Automation.Provider.IValueProvider> должен быть реализован такими элементами управления, как **Палитра** из [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (приведенный ниже), который поддерживает строковое сопоставление между значением цвета (например, "желтый") и эквивалентной внутренней структурой [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)] .  
  
 ![Палитра с отмеченным желтым цветом. ](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Пример сопоставления строки настройки цвета  
  
-   Элемент управления должен иметь свойство <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> , установленное в значение `true` , и свойство <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> , установленное в значение `false` , перед разрешением вызова метода <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-ivalueprovider"></a>Обязательные члены для IValueProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IValueProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|Свойство.|Нет|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|Свойство.|Нет|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|Метод|Нет|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> — Если зависящие от языкового стандарта передается элементу управления в неправильном формате: например, неправильно сформатированная дата.|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> — Если новое значение не может быть преобразовано из строки в формат, распознаваемый элементом управления.|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> — Если попытка управлять элементом управления не включена.|  
  
## <a name="see-also"></a>См. также
- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [TextPattern Insert Text Sample](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
