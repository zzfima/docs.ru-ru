---
title: "Add Content to a Text Box Using UI Automation | Microsoft Docs"
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
  - "adding content to text boxes"
  - "text boxes, adding content"
  - "UI Automation, adding content to text boxes"
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: 13
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 13
---
# Add Content to a Text Box Using UI Automation
> [!NOTE]
>  Эта документация предназначена для разработчиков на платформе .NET Framework, которым требуется использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], определенные в пространстве имен <xref:System.Windows.Automation>.  Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. на веб\-странице [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В данном разделе содержится пример кода, который показывает использование [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для вставки текста в однострочное текстовое поле.  Альтернативный метод предназначен для многострочного текстового поля и текстовых элементов управления, поддерживающих текст в формате RTF, для которых [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] неприменима.  Для сравнения в примере также демонстрируется использование методов Win32, приводящих к таким же результатам.  
  
## Пример  
 Следующий пример проходит через последовательность текстовых элементов управления в целевом приложении.  Каждый текстовый элемент управления проверяется на возможность получения из него объекта класса <xref:System.Windows.Automation.ValuePattern> с помощью метода <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>.  Если текстовый элемент управления поддерживает класс <xref:System.Windows.Automation.ValuePattern>, то для вставки заданной пользователем строки в текстовый элемент управления используется метод <xref:System.Windows.Automation.ValuePattern.SetValue%2A>.  В противном случае используется метод <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=fullName>.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## См. также  
 [TextPattern Insert Text Sample](http://msdn.microsoft.com/ru-ru/67353f93-7ee2-42f2-ab76-5c078cf6ca16)