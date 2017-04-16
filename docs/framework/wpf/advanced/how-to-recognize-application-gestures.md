---
title: "Практическое руководство. Распознавание жестов приложений | Microsoft Docs"
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
  - "жесты приложений, распознавание"
  - "жесты, распознавание"
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Распознавание жестов приложений
В следующем примере демонстрируется операция стирания данных рукописного ввода при выполнении пользователем жеста вычеркивания <xref:System.Windows.Ink.ApplicationGesture> на полотне <xref:System.Windows.Controls.InkCanvas>.  В этом примере предполагается, что полотно <xref:System.Windows.Controls.InkCanvas> с именем `inkCanvas1` объявлено в XAML\-файле.  
  
## Пример  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## См. также  
 <xref:System.Windows.Ink.ApplicationGesture>   
 <xref:System.Windows.Controls.InkCanvas>   
 <xref:System.Windows.Controls.InkCanvas.Gesture>