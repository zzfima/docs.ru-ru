---
title: "Практическое руководство. Установка полей для элементов и элементов управления | Microsoft Docs"
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
  - "Margin - свойство, параметр"
  - "свойства, Margin - свойство"
  - "параметр, Margin - свойство"
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Установка полей для элементов и элементов управления
В этом примере описывается задание свойства <xref:System.Windows.FrameworkElement.Margin%2A> путем изменения в коде программной части значения любого существующего свойства поля.  Свойство <xref:System.Windows.FrameworkElement.Margin%2A> является свойством базового элемента <xref:System.Windows.FrameworkElement>, поэтому оно наследуется множеством элементов управления и других элементов.  
  
 Этот пример написан на [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] с использования файла кода программной части, на который ссылается [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Код программной части показан как в версии [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], так и в [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)].  
  
## Пример  
 [!code-xml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]