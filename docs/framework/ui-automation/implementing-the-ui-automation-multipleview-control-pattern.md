---
title: "Implementing the UI Automation MultipleView Control Pattern | Microsoft Docs"
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
  - "UI Automation, MultipleView control pattern"
  - "MultipleView control pattern"
  - "control patterns, MultipleView"
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# Implementing the UI Automation MultipleView Control Pattern
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.MultipleViewPattern> используется для поддержки элементов управления, которые предоставляют несколько представлений одного набора сведений или дочерних элементов управления и способны переключаться между ними.  
  
 В качестве примеров элементов управления, которые могут предоставлять несколько представлений, можно назвать представление списка \(которое может отображать свое содержимое в виде эскизов, плиток, значков или сведений\), диаграммы [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] \(круговую диаграмму, график, линейчатую диаграмму, диаграмму значений ячеек с формулой\), документы [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] \(обычный, веб\-документ, разметку страницы, макет для чтения, структуру\), календарь [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] \(год, месяц, неделя, день\) и обложки [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)]. Поддерживаемые представления определяются разработчиками элементов управления и относятся к конкретному элементу управления.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Правила и соглашения реализации  
 При реализации шаблона элемента управления Multiple View обратите внимание на следующие правила и соглашения.  
  
-   <xref:System.Windows.Automation.Provider.IMultipleViewProvider> также должен быть реализован в контейнере, который управляет текущим представлением, если он отличается от элемента управления, обеспечивающего текущее представление. Например, проводник содержит элемент управления "Список" для текущего содержимого папки, а представлением для этого элемента управления управляет приложение проводника.  
  
-   Элемент управления, который может сортировать свое содержимое, не считается поддерживающим несколько представлений.  
  
-   Коллекция представлений должна быть идентичной во всех экземплярах.  
  
-   Имена представлений должны быть подходящими для использования в приложениях преобразования текста в речь, шрифта Брайля и других приложениях для удобства чтения.  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## Обязательные члены для IMultipleViewProvider  
 Следующие свойства и методы обязательны для реализации IMultipleViewProvider.  
  
|Обязательные члены|Тип члена|Примечания|  
|------------------------|---------------|----------------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|Метод|Нет|  
  
 Отсутствуют события, связанные с этим шаблоном элемента управления.  
  
<a name="Exceptions"></a>   
## Исключения  
 Поставщик должен вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|-------------|  
|<xref:System.ArgumentException>|Когда метод <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> или <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> вызывается с параметром, который не является членом коллекции поддерживаемых представлений.|  
  
## См. также  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)