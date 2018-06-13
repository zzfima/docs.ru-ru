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
ms.openlocfilehash: 689c8187fcf17ef48a73bc5a6fc4928f3be1a078
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559719"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="c721a-102">Практическое руководство. Определение пространства имен</span><span class="sxs-lookup"><span data-stu-id="c721a-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="c721a-103">Для анимации с <xref:System.Windows.Media.Animation.Storyboard> в коде, необходимо создать <xref:System.Windows.NameScope> и зарегистрировать имена целевых объектов с элементом, который владеет этой областью имен.</span><span class="sxs-lookup"><span data-stu-id="c721a-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="c721a-104">В следующем примере <xref:System.Windows.NameScope> создается для `myMainPanel`.</span><span class="sxs-lookup"><span data-stu-id="c721a-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="c721a-105">Две кнопки `button1` и `button2`, добавляются в панели, а также их имена, которые зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="c721a-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="c721a-106">Несколько анимаций и <xref:System.Windows.Media.Animation.Storyboard> создаются.</span><span class="sxs-lookup"><span data-stu-id="c721a-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="c721a-107">Раскадровки <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод используется для запуска анимаций.</span><span class="sxs-lookup"><span data-stu-id="c721a-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="c721a-108">Поскольку `button1`, `button2`, и `myMainPanel` все используют одну область имен, можно использовать один из них с <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод для запуска анимаций.</span><span class="sxs-lookup"><span data-stu-id="c721a-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c721a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="c721a-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="c721a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c721a-110">See Also</span></span>  
 [<span data-ttu-id="c721a-111">Анимация свойства с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="c721a-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="c721a-112">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="c721a-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
