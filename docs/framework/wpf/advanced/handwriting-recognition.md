---
title: "Распознавание рукописного ввода | Microsoft Docs"
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
  - "распознавание рукописного ввода"
  - "распознавание рукописного ввода"
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Распознавание рукописного ввода
В этом разделе рассматриваются основы распознавания, относящегося к цифровым рукописным данным платформы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Решения распознавания  
 В следующем примере показано распознавание рукописного ввода с помощью <xref:System.Windows.Ink.InkAnalyzer>.  
  
> [!NOTE]
>  В этом примере необходимо, чтобы распознаватели рукописного ввода были установлены в системе.  
  
 Создайте новый проект приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в Visual Studio 2005 с именем InkRecognition.  Замените содержимое файла Window1.XAML следующим кодом XAML.  Этот код создает пользовательский интерфейс пользователя.  
  
 [!code-xml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Добавьте ссылку на сборки WPF Ink Analysis, IAWinFX.dll IACore.dll и IALoader.dll, которые можно найти в \\Program Files\\Reference Assemblies\\Microsoft\\Tablet PC\\v1.7.  Замените содержимое кода программной части следующим кодом.  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Ink.InkAnalyzer>   
 <xref:System.Windows.Ink.AnalysisStatus>   
 <xref:System.Windows.Controls.InkCanvas>