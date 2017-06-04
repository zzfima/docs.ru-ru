---
title: "Implementing the UI Automation Window Control Pattern | Microsoft Docs"
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
  - "control patterns, Window"
  - "UI Automation, Window control pattern"
  - "Window control pattern"
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
caps.latest.revision: 21
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 20
---
# Implementing the UI Automation Window Control Pattern
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IWindowProvider>, включая сведения о свойствах, методах и событиях <xref:System.Windows.Automation.WindowPattern>. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.WindowPattern> используется для поддержки элементов управления, обеспечивающих фундаментальные функциональные возможности на основе окон в традиционном [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]. В качестве примеров элементов управления, которые должны реализовывать этот шаблон элемента управления, можно назвать окна приложения верхнего уровня, дочерние окна [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)], элементы управления "Область разделения с возможностью изменения размера", модальные диалоговые окна и окна всплывающей справки.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Правила и соглашения реализации  
 При реализации шаблона элемента управления Window обратите внимание на следующие правила и соглашения.  
  
-   Для поддержки возможности изменения размера окна и его положения на экране с помощью модели автоматизации пользовательского интерфейса элемент управления должен реализовать <xref:System.Windows.Automation.Provider.ITransformProvider> в дополнение к <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
-   Элементы управления, содержащие заголовки окон и элементы этих заголовков, позволяющие перемещать, разворачивать, сворачивать, закрывать элемент управления или изменять его размер, обычно должны реализовывать <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
-   Такие элементы управления, как всплывающие подсказки, поля со списком или раскрывающиеся меню, обычно не реализуют <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
-   Окна всплывающей справки отличаются от обычных всплывающих подсказок тем, что предоставляют кнопку закрытия окна.  
  
-   IWindowProvider не поддерживает полноэкранный режим, так как он зависит от компонентов в приложении и не является типичным поведением окна.  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## Обязательные члены для IWindowProvider  
 Следующие свойства, методы и события обязательны для реализации интерфейса IWindowProvider.  
  
|Обязательный член|Тип члена|Примечания|  
|-----------------------|---------------|----------------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|Событие|Нет|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|Событие|Нет|  
|<xref:System.Windows.Automation.WindowInteractionState>|Событие|Не гарантируется, что будет <xref:System.Windows.Automation.WindowInteractionState>|  
  
<a name="Exceptions"></a>   
## Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|-------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> -   Если элемент управления не поддерживает запрошенное поведение.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> -   Если параметр не является допустимым числом.|  
  
## См. также  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)