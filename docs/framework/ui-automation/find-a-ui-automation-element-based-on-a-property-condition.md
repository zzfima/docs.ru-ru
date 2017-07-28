---
title: "Find a UI Automation Element Based on a Property Condition | Microsoft Docs"
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
  - "elements, finding by property conditions"
  - "UI Automation, finding elements by property conditions"
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Find a UI Automation Element Based on a Property Condition
> [!NOTE]
>  Эта документация предназначена для разработчиков на платформе .NET Framework, которым требуется использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], определенные в пространстве имен <xref:System.Windows.Automation>.  Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. на веб\-странице [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержится пример кода, который показывает, как найти элемент в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] на основе конкретного свойства или свойств.  
  
## Пример  
 В следующем примере задается набор состояний свойства, которые идентифицируют определенный элемент \(или элементы\) в дереве <xref:System.Windows.Automation.AutomationElement>.  Поиск всех соответствующих элементов затем выполняется с помощью метода <xref:System.Windows.Automation.AutomationElement.FindAll%2A>, который включает ряд логических операций <xref:System.Windows.Automation.AndCondition>, чтобы ограничить число соответствующих элементов.  
  
> [!NOTE]
>  При поиске с <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, вы должны попробовать получить только прямые потомки.  В процессе поиска потомков могут перебираться сотни или даже тысячи элементов, что может привести к переполнению стека.  При попытке получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## См. также  
 [InvokePattern and ExpandCollapsePattern Menu Item Sample](http://msdn.microsoft.com/ru-ru/b7fa141c-e2d1-4da2-a27f-81a7d1172210)   
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)   
 [Use the AutomationID Property](../../../docs/framework/ui-automation/use-the-automationid-property.md)