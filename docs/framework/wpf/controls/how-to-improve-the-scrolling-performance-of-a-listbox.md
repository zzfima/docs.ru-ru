---
title: "Практическое руководство. Улучшение производительности прокрутки ListBox | Microsoft Docs"
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
  - "ListBox - элемент управления [WPF], повышение скорости прокрутки"
  - "ListBox - элемент управления [WPF], повторное использование контейнеров элементов"
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Улучшение производительности прокрутки ListBox
Если <xref:System.Windows.Controls.ListBox> содержит много элементов, ответ пользовательского интерфейса может замедлиться при прокрутке пользователем <xref:System.Windows.Controls.ListBox> с помощью колеса мыши или перетаскивания ползунка в полосе прокрутки.  Можно улучшить производительность <xref:System.Windows.Controls.ListBox>, если пользователь выполняет прокрутку с помощью установки для вложенного свойства <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> значения <xref:System.Windows.Controls.VirtualizationMode>.  
  
## Пример  
  
## Описание  
 В следующем примере создается <xref:System.Windows.Controls.ListBox> и для свойства <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> устанавливается значение <xref:System.Windows.Controls.VirtualizationMode>, чтобы улучшить производительность во время прокрутки.  
  
## Код  
 [!code-xml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 В следующем примере показаны данные, использовавшиеся в предыдущем примере.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]