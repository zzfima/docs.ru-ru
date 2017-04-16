---
title: "Implementing the UI Automation RangeValue Control Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "control patterns, Range Value"
  - "Range Value control pattern"
  - "UI Automation, Range Value control pattern"
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Implementing the UI Automation RangeValue Control Pattern
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IRangeValueProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.RangeValuePattern> используется для поддержки элементов управления, для которых можно установить значение из диапазона. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Правила и соглашения реализации  
 При реализации шаблона элемента управления Range Value обратите внимание на следующие правила и соглашения.  
  
-   Элементы управления позволяют повторную калибровку своих поддерживаемых свойств на основе языкового стандарта или предпочтений пользователя. Примером этого является элемент управления "Термометр", который можно задать для отображения температуры в шкале Цельсия или Фаренгейта.  
  
-   Элементы управления, имеющие неоднозначные значения диапазона, такие как индикаторы выполнения или ползунки, должны нормализовать эти значения.  
  
 ![Индикатор выполнения.](../../../docs/framework/ui-automation/media/uia-rangevaluepattern-progress-bar.PNG "UIA\_RangeValuePattern\_Progress\_Bar")  
Пример индикатора выполнения, где значение имеет тип Integer, а минимальное и максимальное значения свойства нормализованы до 0 и 100 соответственно  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>   
## Обязательные члены для IRangeValueProvider  
  
|Обязательный член|Тип члена|Примечания|  
|-----------------------|---------------|----------------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|Свойство|Нет|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|Свойство|Нет|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|Свойство|Нет|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|Свойство|Нет|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|Свойство|Нет|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|Свойство|Нет|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|Методы|Нет|  
  
 Этот шаблон элемента управления не имеет связанных событий.  
  
<a name="Exceptions"></a>   
## Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|-------------|  
|<xref:System.ArgumentOutOfRangeException>|Метод <xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> вызывается со значением либо больше, чем <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>, либо меньше, чем <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.|  
  
## См. также  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)