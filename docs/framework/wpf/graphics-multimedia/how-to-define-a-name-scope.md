---
title: "Практическое руководство. Определение пространства имен"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d3199de53f93f07e36e7a6e0a02ed9e80b4d591
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-name-scope"></a>Практическое руководство. Определение пространства имен
Для анимации с <xref:System.Windows.Media.Animation.Storyboard> в коде, необходимо создать <xref:System.Windows.NameScope> и зарегистрировать имена целевых объектов с элементом, который владеет этой областью имен. В следующем примере <xref:System.Windows.NameScope> создается для `myMainPanel`. Две кнопки `button1` и `button2`, добавляются в панели, а также их имена, которые зарегистрированы. Несколько анимаций и <xref:System.Windows.Media.Animation.Storyboard> создаются. Раскадровки <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод используется для запуска анимаций.  
  
 Поскольку `button1`, `button2`, и `myMainPanel` все используют одну область имен, можно использовать один из них с <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод для запуска анимаций.  
  
## <a name="example"></a>Пример  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>См. также  
 [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
