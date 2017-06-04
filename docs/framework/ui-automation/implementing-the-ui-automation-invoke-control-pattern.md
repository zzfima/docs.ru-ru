---
title: "Implementing the UI Automation Invoke Control Pattern | Microsoft Docs"
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
  - "UI Automation, Invoke control pattern"
  - "control patterns, Invoke"
  - "Invoke control pattern"
ms.assetid: e5b1e239-49f8-468e-bfec-1fba02ec9ac4
caps.latest.revision: 31
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 30
---
# Implementing the UI Automation Invoke Control Pattern
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IInvokeProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.InvokePattern> используется для поддержки элементов управления, которые не сохраняют состояние при активации, а инициируют или выполняют одно однозначное действие. Элементы управления, сохраняющие свое состояние, такие как флажки и переключатели, вместо этого должны реализовывать <xref:System.Windows.Automation.Provider.IToggleProvider> и <xref:System.Windows.Automation.Provider.ISelectionItemProvider> соответственно. Примеры элементов управления, реализующих шаблон элемента управления Invoke, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Правила и соглашения реализации  
 При реализации шаблона элемента управления Invoke обратите внимание на следующие правила и соглашения.  
  
-   Элементы управления реализуют <xref:System.Windows.Automation.Provider.IInvokeProvider>, если то же самое поведение не доступно через другого поставщика шаблона элемента управления. Например, если метод <xref:System.Windows.Automation.InvokePattern.Invoke%2A> в элементе управления выполняет те же действия, что и метод <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> или <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> этот элемент управления не должен реализовывать <xref:System.Windows.Automation.Provider.IInvokeProvider>.  
  
-   Обычно для вызова элемента управления нужно щелкнуть, дважды щелкнуть, нажать клавишу ВВОД, нажать стандартное сочетание клавиш или нажать некоторое другую другое сочетание клавиш.  
  
-   <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> вызывается в элементе управления, который был активирован \(в ответ на выполнение элементом управления связанного действия\). Если это возможно, событие должно вызываться после завершения действия элементом управления и его возврата без блокировки. Событие Invoked должно вызываться перед обслуживанием запроса Invoke в следующих случаях:  
  
    -   невозможно или нецелесообразно ожидать завершения действия;  
  
    -   действие требует взаимодействия с пользователем;  
  
    -   действие занимает много времени и приведет к блокировке вызывающего клиента на значительное время.  
  
-   Если вызов элемента управления имеет существенные побочные эффекты, эти эффекты должны предоставляться через свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>. Например, несмотря на то что метод <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> не связан с выделением, <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> может привести к выделению другого элемента управления.  
  
-   Эффекты наведения указателя обычно не представляют собой событие Invoked. Однако элементы управления, выполняющие действие \(в отличие от вызывающих визуальный эффект\) на основе состояния наведения, должны поддерживать шаблон элемента управления <xref:System.Windows.Automation.InvokePattern>.  
  
> [!NOTE]
>  Эта реализация считается проблемой специальных возможностей, если элемент управления может быть вызван только в результате побочного эффекта, связанного с мышью.  
  
-   Вызов элемента управления отличается от выбора элемента. Тем не менее в зависимости от элемента управления его вызов может привести к выбору элемента в качестве побочного эффекта. Например, вызов элемента списка документа [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] в папке "Мои документы" одновременно выбирает элемент и открывает документ.  
  
-   Элемент может исчезнуть из дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] сразу после вызова. В результате запрос информации из элемента, предоставленного обратным вызовом события, может завершиться неудачно. В качестве обходного решения рекомендуется выполнять предварительное кэширование информации.  
  
-   Элементы управления могут реализовывать множество шаблонов элементов управления. Например, элемент управления Fill Color \(выбор цвета заливки\) в панели инструментов [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] реализует шаблоны элементов управления <xref:System.Windows.Automation.InvokePattern> и <xref:System.Windows.Automation.ExpandCollapsePattern>.<xref:System.Windows.Automation.ExpandCollapsePattern> предоставляет меню, а <xref:System.Windows.Automation.InvokePattern> заполняет активный выделенный фрагмент выбранным цветом.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## Обязательные члены для IInvokeProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IInvokeProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|------------------------|---------------|----------------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>|метод|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> является асинхронным вызовом и должен возвращаться немедленно без блокировки.<br /><br /> Это особенно важно для элементов управления, которые при вызове прямо или косвенно запускают модальное диалоговое окно. Любой клиент автоматизации пользовательского интерфейса, инициировавший это событие, будет оставаться заблокированным до закрытия модального диалогового окна.|  
  
<a name="Exceptions"></a>   
## Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|-------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|Если элемент управления не включен.|  
  
## См. также  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Invoke a Control Using UI Automation](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)