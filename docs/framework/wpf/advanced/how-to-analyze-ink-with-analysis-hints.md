---
title: "Практическое руководство. Анализ данных рукописного ввода с помощью подсказок анализа | Microsoft Docs"
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
  - "AnalysisHintNode - объекты"
  - "анализ рукописного ввода"
  - "рукописный ввод, AnalysisHintNode - объекты"
  - "рукописный ввод, анализ"
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Анализ данных рукописного ввода с помощью подсказок анализа
узел <xref:System.Windows.Ink.AnalysisHintNode> предоставляет подсказку для средства <xref:System.Windows.Ink.InkAnalyzer>, к которому он присоединен.  Подсказка применяется к области, указанной в свойстве <xref:System.Windows.Ink.ContextNode.Location%2A> узла <xref:System.Windows.Ink.AnalysisHintNode>, и предоставляет дополнительные данные анализатору рукописного ввода для повышения точности распознавания.  Анализатор <xref:System.Windows.Ink.InkAnalyzer> применяет эти сведения, полученные из области подсказок, при анализе рукописного ввода.  
  
## Пример  
 Следующий пример представляет собой приложение, использующее несколько объектов <xref:System.Windows.Ink.AnalysisHintNode> в форме, которая допускает входные данные от устройства рукописного ввода.  Приложение использует свойство <xref:System.Windows.Ink.AnalysisHintNode.Factoid%2A> для предоставления сведений о контексте для каждой записи в форме.  Приложение использует фоновый анализ для анализа рукописных данных и удаляет с формы все рукописные данные через пять секунд после прекращения пользователем добавления данных рукописного ввода.  
  
 [!code-xml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]