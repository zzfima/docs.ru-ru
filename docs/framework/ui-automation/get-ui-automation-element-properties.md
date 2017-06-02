---
title: "Get UI Automation Element Properties | Microsoft Docs"
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
  - "properties, retrieving"
  - "UI Automation, retrieving properties of elements"
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: 5
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 5
---
# Get UI Automation Element Properties
> [!NOTE]
>  Эта документация предназначена для разработчиков на платформе .NET Framework, которым требуется использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], определенные в пространстве имен <xref:System.Windows.Automation>.  Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. на веб\-странице [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе показано, как извлечь свойства элемента [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
### Получение текущего значения свойства  
  
1.  Примените объект <xref:System.Windows.Automation.AutomationElement>, свойство которого нужно получить.  
  
2.  Вызовите метод <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> или извлеките структуру свойства <xref:System.Windows.Automation.AutomationElement.Current%2A> и значение из одного из его членов.  
  
### Получение кэшированного значения свойства  
  
1.  Примените объект <xref:System.Windows.Automation.AutomationElement>, свойство которого нужно получить.  Свойство должно быть указано в объекте <xref:System.Windows.Automation.CacheRequest>.  
  
2.  Вызовите метод <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> или извлеките структуру свойства <xref:System.Windows.Automation.AutomationElement.Cached%2A> и значение из одного из его членов.  
  
## Пример  
 В следующем примере показаны различные способы извлечения текущих свойств объекта <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## См. также  
 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)   
 [Caching in UI Automation Clients](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)