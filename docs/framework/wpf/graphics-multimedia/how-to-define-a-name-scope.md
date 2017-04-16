---
title: "Практическое руководство. Определение пространства имен | Microsoft Docs"
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
  - "анимация, Раскадровки, в процедурном коде"
  - "область видимости имени, определение"
  - "Раскадровки, анимация в процедурном коде"
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Определение пространства имен
Для анимации с <xref:System.Windows.Media.Animation.Storyboard> в коде необходимо создать <xref:System.Windows.NameScope> и зарегистрировать нужные имена объектов с элементом, который владеет этой областью имен.  В следующем примере <xref:System.Windows.NameScope> создается для `myMainPanel`.  На панель добавляются две кнопки — `button1` и `button2`, а их имена регистрируются.  Создаются несколько эффектов анимации и <xref:System.Windows.Media.Animation.Storyboard>.  Метод раскадровки <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> используется для запуска анимаций.  
  
 Поскольку `button1`, `button2` и `myMainPanel` разделяют одну область имен, каждый из них может использоваться с методом <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> для запуска анимаций.  
  
## Пример  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## См. также  
 [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)