---
title: "Практическое руководство. Нахождение элемента по его имени | Microsoft Docs"
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
  - "элементы, поиск по имени"
  - "FindName - метод"
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Нахождение элемента по его имени
В этом примере описывается использование метода <xref:System.Windows.FrameworkElement.FindName%2A> для нахождения элемента по значению свойства <xref:System.Windows.FrameworkElement.Name%2A>.  
  
## Пример  
 В этом примере метод для поиска определенного элемента по его имени записан как обработчик событий для кнопки.  Значение `stackPanel` является именем <xref:System.Windows.FrameworkElement.Name%2A> корневого искомого объекта <xref:System.Windows.FrameworkElement>, метод в примере затем визуально указывает найденный элемент, приводя его к объекту <xref:System.Windows.Controls.TextBlock> и изменяя одно из видимых свойств объекта <xref:System.Windows.Controls.TextBlock> \([!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\).  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]