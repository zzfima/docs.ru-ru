---
title: "Практическое руководство. Определение шаблона GroupBox | Microsoft Docs"
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
  - "элементы управления, GroupBox"
  - "GroupBox - элемент управления, создание шаблонов"
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Определение шаблона GroupBox
В этом примере показано, как создать шаблон для элемента управления <xref:System.Windows.Controls.GroupBox>.  
  
## Пример  
 В следующем примере определяется шаблон элемента управления <xref:System.Windows.Controls.GroupBox> с помощью элемента управления <xref:System.Windows.Controls.Grid> для макета.  В шаблоне используется <xref:System.Windows.Controls.BorderGapMaskConverter> для определения границ <xref:System.Windows.Controls.GroupBox> таким образом, чтобы граница не скрывала содержимое <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.  
  
 [!code-xml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## См. также  
 <xref:System.Windows.Controls.GroupBox>   
 [GroupBox How\-to Topics](http://msdn.microsoft.com/ru-ru/7692e155-a4c6-428c-b7e0-64b3740daca7)