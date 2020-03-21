---
title: Реализация шаблона элемента управления Scroll для автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll control pattern
- control patterns, Scroll
- Scroll control pattern
ms.assetid: 73d64242-6cbb-424c-92dd-dc69530b7899
ms.openlocfilehash: 0420adaefb91f0c9f0d34d5bdf5863373a0b652b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180148"
---
# <a name="implementing-the-ui-automation-scroll-control-pattern"></a>Реализация шаблона элемента управления Scroll для автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IScrollProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.ScrollPattern> используется для поддержки элемента управления, который выступает в качестве прокручиваемого контейнера для коллекции дочерних объектов. Этому элементу управления не обязательно использовать полосы прокрутки для поддержки функции прокрутки, хотя обычно это делается.  
  
 ![Элемент управления прокруткой без полос прокрутки.](./media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")  
Пример элемента управления прокрутки, не использующего полосы прокрутки  
  
 Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Scroll обратите внимание на следующие правила и соглашения.  
  
- Дочерние элементы данного элемента управления должны реализовывать <xref:System.Windows.Automation.Provider.IScrollItemProvider>.  
  
- Полосы прокрутки контейнерного элемента управления не поддерживают шаблон элемента управления <xref:System.Windows.Automation.ScrollPattern> . Вместо него они должны поддерживать шаблон элемента управления <xref:System.Windows.Automation.RangeValuePattern> .  
  
- Если прокрутка измеряется в процентах, все значения или величины, связанные с делением шкалы прокрутки, должны быть нормализованы в диапазоне от 0 до 100.  
  
- Свойства<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> и <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> не зависят от <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>.  
  
- Если свойство <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> = `false` , то свойство <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> должно иметь значение 100 %, а свойство <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> должно иметь значение <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. Аналогично, если свойство <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> = `false` , то свойство <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> должно иметь значение 100 %, а свойство <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> должно иметь значение <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. Это позволяет клиенту автоматизации пользовательского интерфейса использовать эти значения свойств в методе <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> , избегая [состояния гонки](https://support.microsoft.com/default.aspx?scid=kb;en-us;317723) , если клиент не заинтересован в активации прокрутки.  
  
- <xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A> зависит от конкретного языка. Установка HorizontalScrollPercent = 100.0 должна задавать расположение прокрутки элемента управления в крайней правой позиции для таких языков, как английский, где чтение выполняется слева направо. И наоборот, для таких языков, как арабский, где чтение выполняется справа налево, установка HorizontalScrollPercent = 100.0 должен задавать расположение прокрутки в крайней левой позиции.  
  
<a name="Required_Members_for_IScrollProvider"></a>
## <a name="required-members-for-iscrollprovider"></a>Обязательные члены для IScrollProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IScrollProvider>.  
  
|Обязательный член|Тип члена|Примечания|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalScrollPercent%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalViewSize%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalViewSize%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontallyScrollable%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticallyScrollable%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A>|Метод|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>|Метод|None|  
  
 Этот шаблон элемента управления не имеет связанных событий.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|Метод<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> вызывает данное исключение, если элемент управления поддерживает значения <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> исключительно для горизонтальной или вертикальной прокрутки, но передано значение <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> .|  
|<xref:System.ArgumentException>|Метод<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> вызывает данное исключение, если передается значение, которое невозможно преобразовать к типу double.|  
|<xref:System.ArgumentOutOfRangeException>|Метод<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> создает исключение, если переданное значение меньше 0 или больше 100 (за исключением -1, что эквивалентно <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>).|  
|<xref:System.InvalidOperationException>|Оба метода, <xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> и <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> , вызывают это исключение при попытке прокрутки в неподдерживаемом направлении.|  
  
## <a name="see-also"></a>См. также раздел

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
