---
title: "Практическое руководство. Получение возвращаемого значения функции страницы | Microsoft Docs"
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
  - "функции, получение возвращаемых значений"
  - "получение, возвращаемые значения страничных функций"
  - "страничные функции, получение возвращаемых значений"
  - "возвращаемые значения страничных функций"
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Получение возвращаемого значения функции страницы
В этом примере демонстрируется получение результата, возвращаемого функцией страницы.  
  
## Пример  
 Чтобы получить результат, возвращаемый функцией страницы, необходимо обработать <xref:System.Windows.Navigation.PageFunction%601.Return> функции вызываемой страницы.  
  
 [!code-xml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## См. также  
 <xref:System.Windows.Navigation.PageFunction%601>