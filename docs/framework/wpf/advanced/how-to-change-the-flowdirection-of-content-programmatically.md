---
title: "Как изменить FlowDirection содержимого программными средствами | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "документы, свойство FlowDirection - программное изменение"
  - "FlowDirection - cвойство, программное изменение"
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Как изменить FlowDirection содержимого программными средствами
В этом примере демонстрируется, как программно изменить свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> объекта <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## Пример  
 Создаются два элемента <xref:System.Windows.Controls.Button>, каждый из которых представляет одно из возможных значений <xref:System.Windows.FlowDirection>.  При нажатии кнопки значение связанного свойства применяется к содержимому <xref:System.Windows.Controls.FlowDocumentReader> с именем `tf1`.  Значение свойства также записано объекте <xref:System.Windows.Controls.TextBlock> с именем `txt1`.  
  
 [!code-xml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## Пример  
 События, связанные с нажатием кнопки, определенные выше, обрабатываются в файле с выделенным кодом [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)].  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]