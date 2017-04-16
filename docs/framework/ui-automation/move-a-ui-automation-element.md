---
title: "Move a UI Automation Element | Microsoft Docs"
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
  - "moving elements"
  - "elements, moving"
  - "UI Automation, moving elements"
ms.assetid: 4042cb44-e27e-4a03-ac36-9be1eed65b47
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Move a UI Automation Element
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом примере показано, как переместить элемент [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]в указанное место на экране.  
  
## Пример  
 В следующем примере с помощью шаблонов элементов управления <xref:System.Windows.Automation.WindowPattern> и <xref:System.Windows.Automation.TransformPattern> выполняется программное перемещение целевого приложения [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] в отдельные места экрана и отслеживание <xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> <xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent>.  
  
 [!code-csharp[WindowMove#1301](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1301)]
 [!code-vb[WindowMove#1301](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1301)]  
[!code-csharp[WindowMove#1300](../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowMove/CSharp/WindowMove.cs#1300)]
[!code-vb[WindowMove#1300](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowMove/VisualBasic/windowmove.vb#1300)]  
  
## См. также  
 [WindowPattern Sample](http://msdn.microsoft.com/ru-ru/598b695c-8baf-406e-bbfb-2a1c7842a1de)