---
title: "Get the Toggle State of a Check Box Using UI Automation | Microsoft Docs"
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
  - "UI Automation, getting toggle states of check boxes"
  - "check boxes, getting toggle states of"
  - "getting, toggle states of check boxes"
ms.assetid: 84fc31a3-175f-4e93-90a0-dd29d89b77ce
caps.latest.revision: 10
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 10
---
# Get the Toggle State of a Check Box Using UI Automation
> [!NOTE]
>  Эта документация предназначена для разработчиков на платформе .NET Framework, которым требуется использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], определенные в пространстве имен <xref:System.Windows.Automation>.  Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. на веб\-странице [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)], чтобы получить состояние элемента управления.  
  
## Пример  
 В этом примере используется метод <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> класса <xref:System.Windows.Automation.AutomationElement> для получения объекта <xref:System.Windows.Automation.TogglePattern> из элемента управления и возврата его свойства <xref:System.Windows.Automation.ToggleState>.  
  
 [!code-csharp[NavigatingWithTreeWalker#1200](../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigatingWithTreeWalker/CSharp/ClientClass.cs#1200)]
 [!code-vb[NavigatingWithTreeWalker#1200](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigatingWithTreeWalker/visualbasic/clientclass.vb#1200)]