---
title: "Получение шаблонов элементов управления, поддерживающих модель автоматизации пользовательского интерфейса | Microsoft Docs"
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
  - "шаблоны элементов управления в начало"
  - "Получение шаблонов элементов управления автоматизации пользовательского интерфейса"
  - "получение шаблонов элементов управления"
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: 10
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 10
---
# Получение шаблонов элементов управления, поддерживающих модель автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, которые хотят использовать управляемый [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] классы, определенные в <xref:System.Windows.Automation> пространства имен. Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в разделе [API автоматизации Windows: автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе показано, как извлекать объекты шаблона элемента управления из [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элементы.  
  
### <a name="obtain-all-control-patterns"></a>Получение всех шаблонов элементов управления  
  
1.  Получить <xref:System.Windows.Automation.AutomationElement> шаблоны элементов управления которого вам нужны.  
  
2.  Вызов <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> для получения всех шаблонов элементов управления из элемента.  
  
> [!CAUTION]
>  Настоятельно рекомендуется не использовать клиент <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>. Производительность может значительно снизится, как этот метод вызывает метод <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> внутренне для каждого существующего шаблона элемента управления. Если это возможно, клиент должен вызывать <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> для основных шаблонов.  
  
### <a name="obtain-a-specific-control-pattern"></a>Получение конкретного шаблона элемента управления  
  
1.  Получить <xref:System.Windows.Automation.AutomationElement> шаблоны элементов управления которого вам нужны.  
  
2.  Вызов <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> или <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> для запроса определенного шаблона. Эти методы похожи, но если шаблон не найден, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> вызывает исключение, и <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> возвращает `false`.  
  
## <a name="example"></a>Пример  
 В следующем примере извлекается <xref:System.Windows.Automation.AutomationElement> для элемента списка и получает <xref:System.Windows.Automation.SelectionItemPattern> из этого элемента.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>См. также  
 [Шаблоны модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)