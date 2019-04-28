---
title: Практическое руководство. Определение пространства имен
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: a03f477dd31909e8cb9dde9cd29da6f38d665758
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904154"
---
# <a name="how-to-define-a-name-scope"></a>Практическое руководство. Определение пространства имен
Для анимации с <xref:System.Windows.Media.Animation.Storyboard> в коде, необходимо создать <xref:System.Windows.NameScope> и регистрировать имена целевых объектов с элементом, который является владельцем этого пространства имен. В следующем примере <xref:System.Windows.NameScope> создается для `myMainPanel`. Две кнопки `button1` и `button2`, добавляются в панели, а также их имена, которые зарегистрированы. Нескольких анимаций и <xref:System.Windows.Media.Animation.Storyboard> создаются. Раскадровки <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод используется для запуска анимаций.  
  
 Так как `button1`, `button2`, и `myMainPanel` все той же области имен, один из них может использоваться с <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод для запуска анимаций.  
  
## <a name="example"></a>Пример  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>См. также

- [Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
