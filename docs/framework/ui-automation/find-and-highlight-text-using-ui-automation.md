---
title: "Find and Highlight Text Using UI Automation | Microsoft Docs"
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
  - "text, highlighting"
  - "finding text"
  - "text, finding"
  - "UI automation, highlighting text"
  - "UI automation, finding text"
  - "highlighting text"
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# Find and Highlight Text Using UI Automation
> [!NOTE]
>  Эта документация предназначена для разработчиков на платформе .NET Framework, которым требуется использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], определенные в пространстве имен <xref:System.Windows.Automation>.  Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. на веб\-странице [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе демонстрируется последовательный поиск и выделение каждого вхождения строки внутри содержимого текстового элемента управления с помощью [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].  
  
## Пример  
 В следующем примере из текстового элемента управления получается объект <xref:System.Windows.Automation.TextPattern>.  После этого объект <xref:System.Windows.Automation.Text.TextPatternRange>, предоставляющий текстовое содержимое всего документа, создается с помощью свойства <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> объекта <xref:System.Windows.Automation.TextPattern>.  Затем создаются два дополнительных объекта <xref:System.Windows.Automation.Text.TextPatternRange>, которые используются для последовательного поиска и выделения.  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## См. также  
 [Find and Highlight Text Using UI Automation](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)